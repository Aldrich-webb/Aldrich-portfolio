<template>
  <nav class="navbar navbar-expand-lg fixed-top">
    <div class="container">
      <a class="navbar-brand" href="#landing">
        DESSTO</a>
      <button
        class="navbar-toggler"
        type="button"
        data-bs-toggle="collapse"
        data-bs-target="#navbarNav"
        aria-controls="navbarNav"
        aria-expanded="false"
        aria-label="Toggle navigation"
      >
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarNav">
        <ul class="navbar-nav ms-auto">
          <li class="nav-item">
            <a class="nav-link" aria-current="page" href="#landing">Home</a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#about">About Me</a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#projects">Projects</a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#skills">My Skills</a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#tools">Tools</a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#contact">Contact</a>
          </li>
        </ul>
      </div>
    </div>
  </nav>
</template>

<script>
export default {
  name: 'Navbar',
};
</script>

<style scoped>
.navbar {
  background-color: #82a0aa; /* From index.css */
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.05);
}

.navbar-brand .logo {
  max-height: 60px; /* Adjusted height for logo as per previous request */
  width: auto;
}

.nav-link {
  font-weight: 600;
  color: #495057 !important; /* From index.css */
  transition: color 0.3s ease;
  position: relative;
}

/* Green highlight on hover, matching previous request */
.nav-link.active,
.nav-link:hover {
  color: #00896f !important; /* Green highlight */
}

/* UI Improvement: Underline effect (adjusted to green) */
.nav-link::after {
  content: '';
  position: absolute;
  bottom: 0;
  left: 0;
  width: 0;
  height: 2px;
  background-color: #00896f; /* Green highlight */
  transition: width 0.3s ease;
}
.nav-link:hover::after,
.nav-link.active::after {
  width: 100%;
}
</style>