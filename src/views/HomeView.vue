<template>
  <div class="container wrapper">
    <div class="home">
      <img class="img" src="@/assets/emppic.png"> 
      <h1 class="title">Nikola Cerovina</h1>
      <div class="moving-title-container">
        <h2 ref="movingTitle" class="yellow dev grad">Frontend Developer</h2>
      </div>
    </div>
    <div class="aboutMe">
      <p>
        <span class="yellow">></span> Hi there, I'm Nikola 👋🏻
        <br>
        <br>
        <span class="yellow">></span> I build apps with JS 🦾 
        <br>
        <br>
        <span class="yellow">></span> Check out my work 🚀
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
      const duration = 2000; 

      gradElements.forEach(element => {
        animate(element, Date.now());
      });

      function animate(element, startTime) {
        function step() {
          const currentTime = Date.now();
          const elapsed = currentTime - startTime;

          const progress = (elapsed % duration) / duration; 

          const opacity = 1 + 0.5 * Math.cos(progress * Math.PI * 2); 
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
    width: 87%;
    margin-top: 30px;
    padding: 30px;
  }

  .title {
    margin: auto;
  }
}

@media (min-width: 767px) {
  .home {
    margin-right: 100px;
  }
  .aboutMe p {
    width: 300px;
    padding: 30px;
    margin-top: 50px;
  }
}

.moving-title-container {
  position: relative;
  height: 50px;
  display: flex;
  justify-content: center;
  align-items: center;
}

.dev {
  margin-bottom: 15px;
  position: absolute;
  font-style: italic;
}

.aboutMe {
  margin-bottom: 35px;
  margin-top: -15px;
  margin-left: -15px;
}

.img {
  margin-top: -15px;
}
</style>