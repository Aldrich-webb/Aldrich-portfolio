<template>
  <section id="about">
    <div class="container">
      <h2>About Me</h2>
      <div class="row align-items-center">
        <div class="col-lg-4 text-center">
          <img src="/images/portfoliopic.png" class="img-fluid about-img" alt="Your Photo" />
        </div>
        <div class="col-lg-7 mt-4 mt-lg-0">
          <p>
            Hello! I'm Dessto, a dedicated software developer who transforms complex problems into elegant digital solutions. I specialize in modern web technologies including HTML, CSS, Bootstrap, JavaScript, Node.js, and etc. My focus is on writing clean, efficient code that delivers exceptional user experiences. I've successfully built responsive websites, e-commerce platforms, and web applications for various clients. Each project teaches me something new and helps me grow as a developer.
          </p>
          <p>
            I enjoy working both independently and as part of collaborative teams. My development process includes careful planning, coding, testing, and deployment. I stay updated with the latest technologies and industry best practices. Problem-solving and attention to detail are at the core of my work approach. My goal is to create software that users love and businesses can depend on.
          </p>
          <p>
            I am always eager to learn new technologies and take on challenging projects. Let's connect and create something amazing together!
          </p>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'About',
};
</script>

<style scoped>
#about .container {
  background-color: #a3cfcd; /* From index.css */
  border-radius: 50px;
  padding: 50px 30px; /* Added padding to make content not stick to edges */
}

.about-img {
  border-radius: 15px;
  box-shadow: 0 8px 16px rgba(0, 0, 0, 0.1);
  margin-bottom: 50px; /* From index.css */
  margin-left: auto; /* Center image */
  margin-right: auto; /* Center image */
  display: block; /* Ensure it respects margins */
  max-width: 100%; /* Ensure responsiveness */
  height: auto;
}

/* Responsive adjustments */
@media (max-width: 768px) {
  .about-img {
    margin-bottom: 30px;
  }
}
</style>