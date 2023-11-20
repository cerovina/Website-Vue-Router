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
            <img class="img1" src="@/assets/taskStore.png" alt="Online Store">
            <br>
            <a class="link" href="https://cerovina.github.io/Task-Online-Store/">Online Store</a>
          </div>
          <div class="grid-item">
            <img class="img1" src="@/assets/formpicture.png" alt="Web Form">
            <br>
            <a class="link" href="https://web-form-vue-lake.vercel.app/">Web Form (Vue)</a>
          </div>
          <div class="grid-item">
            <img class="img1" src="@/assets/yetiii.png" alt="Weather Yeti">
            <br>
            <a class="link" href="https://cerovina.github.io/Weather-Yeti/">Weather Yeti (React)</a>
          </div>
          <div class="grid-item">
            <img class="img1" src="@/assets/bugs.png" alt="Space Shooter">
            <br>
            <a class="link" href="https://cerovina.github.io/Grim-Shooter/">Grim Shooter (p5)</a>
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
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 10px;
  text-align: center;
}

.grid-item {
  flex-basis: calc(30%);
  margin-top: -30px;
  margin-bottom: 65px;
}

.reacttitle {
  color: #ffffff;
  font-family: "Electro";
  margin-top: -5px;
}

.projectP {
  margin-top: 35px;
  margin-bottom: 70px;
  font-family: "Electro";
  color: white;
  font-size: 25px;
  font-style: italic;
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
    display: flex;
    justify-content: space-between;
    align-items: center;
    gap: 10px;
    flex-wrap: wrap;
    text-align: center;
  }

  .grid-item {
    flex-basis: calc(50% - 10px);
    margin-top: -30px;
    margin-bottom: 65px;
  }
}

</style>