<template>
  <div class="container wrapper">
    <div class="home">
      <img class="img" src="@/assets/ncnord.jpg"> 
      <h1 class="title">Nikola Cerovina</h1>
      <div class="moving-title-container">
        <h2 ref="movingTitle" class="yellow dev grad">Front-End Developer</h2>
      </div>
    </div>
    <div class="aboutMe">
      <p>
        <span class="yellow">></span> Proficient in HTML, CSS, and JavaScript. Experienced in Vue and React.
        <br>
        <br>
        <span class="yellow">></span> Familiar with design tools like Figma and creative coding using p5.js.
        <br>
        <br>
        <span class="yellow">></span> Passionate about web development and expanding my skills in the field.
      </p>
    </div>
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
.title {
  margin-top: 15px;
  margin-bottom: 0px;
  font-size: 45px;
}

@media (max-width: 767px) {
  .aboutMe p {
    width: 75%;
    margin-top: 30px;
  }

  .title {
    margin: auto;
  }
}

.moving-title-container {
  position: relative;
  height: 50px; /* Adjust the height as needed */
  display: flex;
  justify-content: center;
  align-items: center;
}

.dev {
  margin-bottom: 15px;
  position: absolute;
  font-style: italic;
}
</style>
