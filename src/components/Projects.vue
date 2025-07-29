<template>
  <section id="projects">
    <div class="container">
      <h2>My Projects</h2>
      <div class="row g-4">
        <div v-for="(project, index) in projects" :key="index" class="col-lg-4 col-md-6">
          <ProjectCard :project="project" />
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import ProjectCard from './ProjectCard.vue';
import projectsData from '../data/projects.json'; // Adjust path as needed

export default {
  name: 'Projects',
  components: {
    ProjectCard,
  },
  data() {
    return {
      projects: projectsData,
    };
  },
};
</script>

<style scoped>
/* No specific styles needed here, as ProjectCard handles individual card styles */
</style>