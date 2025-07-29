<template>
  <footer>
    <div class="container">
      <p>© 2025 Dessto. All rights reserved.</p>
      <div class="social-icons mt-3">
        <a href="https://www.linkedin.com/" aria-label="LinkedIn" target="_blank" rel="noopener noreferrer"><i class="fab fa-linkedin"></i></a>
        <a href="https://github.com/" aria-label="GitHub" target="_blank" rel="noopener noreferrer"><i class="fab fa-github"></i></a>
        <a href="https://discordapp.com/" aria-label="Discord" target="_blank" rel="noopener noreferrer"><i class="fa-brands fa-discord"></i></a>
        <a href="https://www.facebook.com/" aria-label="Facebook" target="_blank" rel="noopener noreferrer"><i class="fab fa-facebook"></i></a>
      </div>
    </div>
  </footer>
</template>

<script>
export default {
  name: 'FooterComponent',
};
</script>

<style scoped>
footer {
  background-color: #343a40; /* From index.css */
  color: white;
  padding: 40px 0;
  text-align: center;
  border-top-left-radius: 50px;
  border-top-right-radius: 50px;
}

.social-icons a {
  color: white;
  font-size: 1.8rem;
  margin: 0 15px;
  transition: color 0.3s ease;
}

.social-icons a:hover {
  color: #007bff; /* From index.css */
}
</style>