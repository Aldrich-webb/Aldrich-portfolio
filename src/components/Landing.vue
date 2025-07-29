<template>
  <section id="landing" class="landing-section d-flex align-items-center">
    <div class="container">
      <h1>Hi, I'm DESSTO – Your Vision, My Code.</h1>
      <p class="lead">I'm a dedicated Full Stack Web Developer passionate about building robust, user-centric web applications. Let's create something exceptional together that drives real results.</p>
      <a href="#projects" class="btn btn-primary-custom bg-light">EXPLORE MY PORTFOLIO</a>
    </div>
  </section>
</template>

<script>
export default {
  name: 'Landing',
};
</script>

<style scoped>
.landing-section {
  background: linear-gradient(to right, #677381, #82a0aa, #677381); /* From index.css */
  color: white;
  padding: 100px 0;
  text-align: center;
  border-bottom-left-radius: 50px;
  border-bottom-right-radius: 50px;
  min-height: 100vh; /* Make it full viewport height */
}

.landing-section h1 {
  font-size: 3.5rem;
  font-weight: 700;
  margin-bottom: 20px;
}

.landing-section p {
  font-size: 1.25rem;
  margin-bottom: 30px;
}

/* Responsive adjustments */
@media (max-width: 768px) {
  .landing-section h1 {
    font-size: 2.5rem;
  }
  .landing-section p {
    font-size: 1rem;
  }
}
</style>