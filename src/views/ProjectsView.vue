<template>
    <div class="projectsWrap">
      <div class="projects">
        <h1 class="heading"><span class="green">PearLink</span> - My Biggest Project</h1>
      </div>
      <section id="portfolio">
        <div class="main-grid">
          <div class="portfolio-item">
            <p class="projectP"><span class="yellow grad">Read about it on my</span> <a class="link" href="https://github.com/cerovina/Email-Client">GitHub</a></p>
            <a class="link" href="https://email-client-theta.vercel.app/">Try it out here (in development...)</a>
          </div>
            <div class="grid-item">
              <img class="img1" src="@/assets/gif-ecli.gif" alt="Online Store">
            </div>
        </div>
      </section>
    </div>
  </template>

<script>
export default {
  name: 'HomeView',
  mounted() {
    this.glowTitle();
  },
  methods: {
    glowTitle() {
      const gradElements = document.querySelectorAll('.yellow');
      const duration = 2000;

      gradElements.forEach(element => {
        animate(element, Date.now());
      });

      function animate(element, startTime) {
        function step() {
          const currentTime = Date.now();
          const elapsed = currentTime - startTime;

          const progress = (elapsed % duration) / duration; // Ensure progress remains in the range [0, 1]

          const opacity = 1 + 0.5 * Math.cos(progress * Math.PI * 2); // Cosine function for a slow glow effect
          element.style.opacity = opacity;

          requestAnimationFrame(step);
        }

        requestAnimationFrame(step);
      }
    },
  },
};
</script>

<style scoped>
.green {
  color: #26A95E;
}

.projectsWrap {
  background-color: #0F0225;
}

.img1 {
  width: 400px;
  height: auto;
  padding: 5px;
  border: 2px solid #81A2C1;
  box-shadow: 0 0 10px #81A2C1;
}

.main-grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  margin-left: 200px;
  justify-content: center;
  align-items: center;
  text-align: center;
  width: 75%;
  height: 470px;
}

.grid-item {
  grid-column: span 0;
  margin-top: 10px;
  margin-bottom: 10px; 
  width: 50%
}

.projectP {
  margin-top: 35px;
  margin-bottom: 30px;
  font-family: "Electro";
  color: white;
  font-size: 25px;
  font-style: italic;
  padding: 30px;
  width: 320px;
}

@media (max-width: 767px) {
  p {
    width: 75%;
  }

  h1{
    margin: auto;
  }

    .img1 {
      width: 75%;
      height: auto;
      padding: 5px;
      border: 2px solid #81A2C1;
      box-shadow: 0 0 10px #81A2C1;
  }

    .main-grid {
      display: grid;
      grid-template-columns: repeat(1, 1fr);
      margin-left: 60px;
      margin-right: 60px;
      justify-content: center; 
      align-items: center;
      text-align: center;
      margin: auto;
  }

    .grid-item {
      grid-column: span 0;
      margin-top: 10px;
      margin-bottom: 10px;
      margin: auto;
  }

    .portfolio-item {
      margin-top: -30px;
    }

    .img1 {
      width: 100%;
    }
}
</style>