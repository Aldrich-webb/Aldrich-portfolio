<template>
  <section id="contact" class="bg-light">
    <div class="container">
      <h2>Get In Touch</h2>
      <div class="row justify-content-center text-center">
        <div class="col-md-4 mb-4">
          <i class="fas fa-envelope contact-icon"></i>
          <h4>Email Me</h4>
          <p><a href="mailto:aldrichwork25@gmail.com">aldrichwork25@gmail.com</a></p>
        </div>
        <div class="col-md-4 mb-4">
          <i class="fas fa-phone-alt contact-icon"></i>
          <h4>Call Me</h4>
          <p><a href="tel:+639687470258">+63 9687470258</a></p>
        </div>
        <div class="col-md-4 mb-4">
          <i class="fas fa-map-marker-alt contact-icon"></i>
          <h4>Location</h4>
          <p>
            <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d123504.49166222103!2d120.97978144023344!3d14.683422970743568!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x3397ba0942ef7375%3A0x4a9a32d9fe083d40!2sQuezon%20City%2C%20Metro%20Manila!5e0!3m2!1sen!2sph!4v1753719945698!5m2!1sen!2sph" width="300" height="300" style="border:0;" allowfullscreen="" loading="lazy" referrerpolicy="no-referrer-when-downgrade"></iframe>
          </p>
        </div>
      </div>
      <div class="row justify-content-center mt-5">
        <div class="col-lg-8">
          <form @submit.prevent="submitForm">
            <div class="mb-3">
              <input type="text" class="form-control rounded-pill" id="name" placeholder="Your Name" required v-model="name" />
            </div>
            <div class="mb-3">
              <input type="email" class="form-control rounded-pill" id="email" placeholder="Your Email" required v-model="email" />
            </div>
            <div class="mb-3">
              <textarea class="form-control rounded-4" id="message" rows="5" placeholder="Your Message" required v-model="message"></textarea>
            </div>
            <div class="d-flex justify-content-center my-3">
                <div ref="recaptchaContainer"></div>
            </div>
            <div class="text-center">
              <button type="submit" class="btn btn-primary-custom bg-secondary text-white" :disabled="isLoading">
                {{ isLoading ? "Sending..." : "Send Message" }}
              </button>
            </div>
          </form>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref, onMounted, onBeforeUnmount } from 'vue';
import { Notyf } = require('notyf');
import 'notyf/notyf.min.css';

const notyf = new Notyf();
const WEB3FORMS_ACCESS_KEY = "046edb61-d16d-42ce-87b7-aa1eac00974a";

const subject = "New message from portfolio contact form";

const name = ref("");
const email = ref("");
const message = ref("");

const isLoading = ref(false);

/**
 * reCAPTCHA Integration
 */
// Replace with your actual reCAPTCHA Site Key from Google reCAPTCHA admin panel
const SITE_KEY = '6Ld_1pIrAAAAALPW69G0F4We4DrPqUJFm50njgT0'; 

const recaptchaContainer = ref(null);
const recaptchaWidgetId = ref(null);
const recaptchaToken = ref('');

// Callback called by reCAPTCHA when successful
function onRecaptchaSuccess(token) {
  recaptchaToken.value = token;
}

// Callback when expired
function onRecaptchaExpired() {
  recaptchaToken.value = '';
}

// Function to render the reCAPTCHA widget
function renderRecaptcha() {
  if (!window.grecaptcha) {
    console.error('reCAPTCHA not loaded, ensure the script is in index.html');
    return;
  }

  // Only render if the container element exists and widget hasn't been rendered yet
  if (recaptchaContainer.value && recaptchaWidgetId.value === null) {
    recaptchaWidgetId.value = window.grecaptcha.render(recaptchaContainer.value, {
      sitekey: SITE_KEY,
      size: 'normal', // or 'compact'
      callback: onRecaptchaSuccess,
      'expired-callback': onRecaptchaExpired,
    });
  }
}

// Function to reset reCAPTCHA
function resetRecaptcha() {
  if (recaptchaWidgetId.value !== null) {
    window.grecaptcha.reset(recaptchaWidgetId.value);
    recaptchaToken.value = '';
  }
}

// submitForm() handler function sends the form data to web3forms and displays notifications.
const submitForm = async () => {
    // Check if reCAPTCHA has been verified
    // if (!recaptchaToken.value) { // <-- This line and the block below it are commented out
    //     notyf.error('Please verify that you are not a robot.');
    //     return; // Stop form submission
    // }

    isLoading.value = true; // Set loading state to true
    try {
        const response = await fetch("https://api.web3forms.com/submit", {
            method: "POST",
            headers: {
                "Content-Type": "application/json",
                Accept: "application/json",
            },
            body: JSON.stringify({
                access_key: WEB3FORMS_ACCESS_KEY,
                subject: subject,
                name: name.value,
                email: email.value,
                message: message.value,
                // Include reCAPTCHA token in the submission if Web3Forms supports it directly
                // 'g-recaptcha-response': recaptchaToken.value // <-- This line is commented out
            }),
        });
        const result = await response.json();

        if (result.success) {
            console.log(result);
            notyf.success("Message Sent!");
            // Clear form fields on success
            name.value = '';
            email.value = '';
            message.value = '';
        } else {
            console.error("Web3Forms submission error:", result);
            notyf.error(result.message || "Failed to send message. Please try again.");
        }
    } catch (error) {
        console.error("Error submitting form:", error);
        notyf.error("An error occurred while sending your message.");
    } finally {
        isLoading.value = false; // Reset loading state
        resetRecaptcha(); // Reset reCAPTCHA widget
    }
};

// Lifecycle Hooks for reCAPTCHA
onMounted(() => {
  // This code waits for the Google reCAPTCHA library to load, then renders the reCAPTCHA widget.
  // The widget is rendered with grecaptcha.render(), which requires a sitekey.
  // Callback functions handle success and expiration events.
  const interval = setInterval(() => {
    if (window.grecaptcha && window.grecaptcha.render) {
      renderRecaptcha();
      clearInterval(interval);
    }
  }, 100);

  onBeforeUnmount(() => {
    clearInterval(interval);
  });
});
</script>

<style scoped>
.contact-icon {
  font-size: 2.5rem;
  color: #007bff;
  margin-bottom: 15px;
}

/* Form control styling to match the provided index.css aesthetic */
.form-control.rounded-pill {
  border-radius: 50rem !important; /* Make it very rounded */
  padding: 0.75rem 1.5rem;
}

.form-control.rounded-4 {
  border-radius: 0.5rem !important; /* Adjust if you want less or more rounded corners */
  padding: 0.75rem 1.5rem;
}

/* Ensure placeholder color is visible */
.form-control::placeholder {
  color: #6c757d; /* Adjust as needed */
  opacity: 1; /* Firefox default is lower opacity */
}
</style>