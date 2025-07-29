<template>
  <section id="tools" class="tools-section">
    <div class="container">
      <h2>Tools</h2>

      <div class="row justify-content-center g-4">
        <div class="col-12 col-md-6 col-lg-4">
          <div class="tool-category">
            <h3>Front End</h3>
            <div class="tool-icons">
              <div class="icon-item">
                <img src="/images/html.png" alt="HTML5 Logo" />
              </div>
              <div class="icon-item">
                <img src="/images/css.jpg" alt="CSS3 Logo" />
              </div>
              <div class="icon-item">
                <img src="/images/bootstrap.jpg" alt="Bootstrap Logo" />
              </div>
              <div class="icon-item">
                <img src="/images/javascript.png" alt="JavaScript Logo" />
              </div>
            </div>
          </div>
        </div>

        <div class="col-12 col-md-6 col-lg-4">
          <div class="tool-category">
            <h3>MERN</h3>
            <div class="tool-icons">
              <div class="icon-item">
                <img src="/images/mongodb.png" alt="MongoDB Logo" />
              </div>
              <div class="icon-item">
                <img src="/images/node.png" alt="Node.js Logo" />
              </div>
            </div>
          </div>
        </div>

        <div class="col-12 col-md-6 col-lg-4">
          <div class="tool-category">
            <h3>Other Tools</h3>
            <div class="tool-icons">
              <div class="icon-item">
                <img src="/images/gitt.jpg" alt="Git Logo" />
              </div>
              <div class="icon-item">
                <img src="/images/sublime.png" alt="Sublime Text Logo" />
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'Tools',
};
</script>

<style scoped>
.tools-section {
  padding: 50px 0;
  text-align: center;
  /* Background color from previous request was #343a40, but index.css implies default.
     Leaving transparent for now to rely on body background or parent section.
     If you want #343a40, uncomment below: */
  /* background-color: #343a40; */
  /* color: #00896f; */
}

.tools-section h2 {
  font-size: 2.5rem;
  margin-bottom: 50px;
  color: #192a56; /* From index.css */
}

.tool-category {
  margin-bottom: 30px;
  text-align: center;
  background-color: white; /* Added background for clarity */
  border-radius: 15px;
  box-shadow: 0 8px 16px rgba(0, 0, 0, 0.08);
  padding: 30px;
}

.tool-category h3 {
  font-size: 1.8rem;
  margin-bottom: 25px;
  color: #192a56; /* From index.css */
  font-weight: 600;
}

.tool-icons {
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
  gap: 30px; /* Increased gap as per previous request */
}

.icon-item {
  width: 90px; /* Increased size a bit for prominence */
  height: 90px;
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: 50%; /* Make them circular */
  overflow: hidden; /* Hide overflow for circular images */
  box-shadow: 0 4px 8px rgba(0,0,0,0.1); /* Subtle shadow */
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.icon-item:hover {
  transform: translateY(-5px) scale(1.05);
  box-shadow: 0 8px 16px rgba(0,0,0,0.2);
}

.icon-item img {
  max-width: 100%;
  max-height: 100%;
  object-fit: contain; /* Ensure image fits within the circle */
}
</style>