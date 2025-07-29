<template>
  <div class="card projects-item">
    <img :src="project.image" class="card-img-top" :alt="project.title" />
    <div class="card-body">
      <h5 class="card-title">{{ project.title }}</h5>
      <p class="card-text">{{ project.description }}</p>
      <p class="card-text">
        <small class="text-muted"><strong>Key Technologies:</strong> {{ project.technologies }}</small>
      </p>
      <a :href="project.link" class="btn btn-sm btn-outline-primary rounded-pill" target="_blank" rel="noopener noreferrer">View Details</a>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ProjectCard',
  props: {
    project: {
      type: Object,
      required: true,
    },
  },
};
</script>

<style scoped>
.card {
  border: none;
  border-radius: 15px;
  box-shadow: 0 8px 16px rgba(0, 0, 0, 0.08);
  transition: transform 0.3s ease, box-shadow 0.3s ease;
  height: 100%; /* Ensure cards in a row have equal height */
  display: flex;
  flex-direction: column;
}

.card:hover {
  transform: translateY(-5px);
  box-shadow: 0 12px 24px rgba(0, 0, 0, 0.15);
}

.card-body {
  padding: 30px;
  flex-grow: 1; /* Allow card body to expand */
  display: flex;
  flex-direction: column;
}

.card-title {
  color: #007bff; /* Matching global h2 color */
  font-weight: 600;
  margin-bottom: 15px;
}

.card-text {
  margin-bottom: 10px;
}

.card-text small {
  color: #6c757d !important; /* Ensure muted text is readable */
}

.projects-item img {
  border-radius: 15px 15px 0 0; /* Only top corners rounded */
  transition: transform 0.3s ease;
  width: 100%;
  height: 200px; /* Fixed height for project images for uniformity */
  object-fit: cover; /* Cover the area, cropping if necessary */
}

.projects-item img:hover {
  transform: scale(1.05);
}

.btn-outline-primary {
  color: #007bff;
  border-color: #007bff;
  transition: all 0.3s ease;
  margin-top: auto; /* Pushes button to the bottom of the card body */
}

.btn-outline-primary:hover {
  background-color: #007bff;
  color: white;
  box-shadow: 0 4px 8px rgba(0, 123, 255, 0.4);
}
</style>