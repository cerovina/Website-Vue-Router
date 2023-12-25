<template>
    <div class="projectsWrap">
      <div class="projects">
        <h1 class="heading">My Projects</h1>
      </div>
      <section id="portfolio">
        <div class="portfolio-item">
          <p class="projectP"><span class="yellow grad">Check out my</span> <a class="link" href="https://github.com/cerovina">GitHub</a></p>
        </div>

        <div class="grid-container">
          <div class="grid-item">
            <img class="img1" src="@/assets/picForm2.png" alt="Web Form">
            <br>
            <a class="link" href="https://web-form-vue-lake.vercel.app/">Web Form</a>
          </div>
          <div class="grid-item">
            <img class="img1" src="@/assets/taskStore.png" alt="Online Store">
            <br>
            <a class="link" href="https://cerovina.github.io/Task-Online-Store/">Online Store</a>
          </div>
          <div class="grid-item">
            <img class="img1" src="@/assets/HemaPic.jpg" alt="HEMA Weapons">
            <br>
            <a class="link" href="https://hema-weapon-showcase.vercel.app/">Weapon Showcase</a>
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
      const duration = 2000; // Adjust the duration as needed (in milliseconds)

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

.projectsWrap {
  background-color: #0F0225;
}

.img1 {
  width: 65%;
  height: auto;
  padding: 5px;
  border: 2px solid #81A2C1;
  box-shadow: 0 0 10px #81A2C1;
}

.grid-container {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  margin-left: 60px;
  margin-right: 60px;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.grid-item {
  grid-column: span 0;
  margin-top: 10px;
  margin-bottom: 10px; 
}

.reacttitle {
  color: #ffffff;
  font-family: "Electro";
  margin-top: -5px;
}

.projectP {
  margin-top: 35px;
  margin-bottom: 30px;
  font-family: "Electro";
  color: white;
  font-size: 25px;
  font-style: italic;
  padding: 10px;
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

    .grid-container {
    display: grid;
    grid-template-columns: repeat(1, 1fr);
    margin-left: 60px;
    margin-right: 60px;
    justify-content: center; /* You can adjust this based on your layout needs */
    align-items: center;
    text-align: center;
  }

    .grid-item {
    grid-column: span 0;
    margin-top: 10px;
    margin-bottom: 10px; 
  }
}

</style>