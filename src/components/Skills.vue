<template>
  <section id="skills" class="bg-light">
    <div class="container">
      <h2>My Skills</h2>
      <div class="row">
        <div class="col-md-6 mb-4">
          <div class="card">
            <div class="card-body">
              <h5 class="card-title text-primary"><i class="fas fa-code"></i> Programming Languages</h5>
              <p class="card-text">
                <span class="skill-badge">HTML5</span>
                <span class="skill-badge">CSS3</span>
                <span class="skill-badge">JavaScript (ES6+)</span>
                <span class="skill-badge">SQL</span>
              </p>
            </div>
          </div>
        </div>
        <div class="col-md-6 mb-4">
          <div class="card">
            <div class="card-body">
              <h5 class="card-title text-primary"><i class="fas fa-database"></i> Databases & Tools</h5>
              <p class="card-text">
                <span class="skill-badge">MongoDB</span>
                <span class="skill-badge">MySQL</span>
                <span class="skill-badge">Git</span>
                <span class="skill-badge">GitHub</span>
                <span class="skill-badge">Sublime Text</span>
                <span class="skill-badge">Figma</span>
              </p>
            </div>
          </div>
        </div>
        <div class="col-md-6 mb-4">
          <div class="card">
            <div class="card-body">
              <h5 class="card-title text-primary"><i class="fas fa-book-open"></i> Frameworks & Libraries</h5>
              <p class="card-text">
                <span class="skill-badge">Bootstrap 5</span>
                <span class="skill-badge">Node.js</span>
              </p>
            </div>
          </div>
        </div>
        <div class="col-md-6 mb-4">
          <div class="card">
            <div class="card-body">
              <h5 class="card-title text-primary"><i class="fas fa-users-cog"></i> Other Skills</h5>
              <p class="card-text">
                <span class="skill-badge">Responsive Design</span>
                <span class="skill-badge">RESTful APIs</span>
                <span class="skill-badge">Problem Solving</span>
                <span class="skill-badge">Team Collaboration</span>
                <span class="skill-badge">Agile Methodologies</span>
              </p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'Skills',
};
</script>

<style scoped>
.card {
  border: none;
  border-radius: 15px;
  box-shadow: 0 8px 16px rgba(0, 0, 0, 0.08);
  transition: transform 0.3s ease, box-shadow 0.3s ease;
  height: 100%; /* Ensure cards have equal height */
}

.card:hover {
  transform: translateY(-5px);
  box-shadow: 0 12px 24px rgba(0, 0, 0, 0.15);
}

.card-title {
  color: #007bff !important; /* Bootstrap text-primary makes it blue */
  margin-bottom: 20px;
  font-weight: 600;
}

.skill-badge {
  background-color: #e9ecef;
  color: #495057;
  padding: 8px 15px;
  border-radius: 20px;
  margin: 5px;
  display: inline-block;
  font-weight: 600;
}
</style>