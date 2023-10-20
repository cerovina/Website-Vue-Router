<template>
  <div class="container">
    <div class="home">
      <img class="img" src="@/assets/ncnord.jpg"> 
      <h1 class="title">Nikola Cerovina</h1>
      <h2 class="yellow dev">Front-End Developer</h2>
    </div>
    <div class="aboutMe">
      <p>
        🚀 Proficient in HTML, CSS, and <span class="grad">JavaScript</span>. Experienced in Vue and React.
        <br>
        <br>
        🎨 Familiar with <span class="grad">design tools</span> like Figma and creative coding using p5.js.
        <br>
        <br>
        🌱 <span class="grad">Passionate</span> about web development and expanding my skills in the field.
      </p>
    </div>
  </div>
</template>


<script>

export default {
  name: 'HomeView',  
  components: {

  }
}
</script>

<style scoped>

.title {
  margin-top: 15px;
  margin-bottom: 0px;
  font-size: 45px;
}

.dev {
  margin-bottom: 50px;
}

</style>