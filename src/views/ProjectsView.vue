<template>
    <div>
      <div class="projects">
        <h1>My Projects</h1>
      </div>
      <section id="portfolio">
        <div class="portfolio-item">
          <p class="projectP"><span class="yellow">Check out my</span> <a class="link" href="https://github.com/cerovina">GitHub</a></p>
        </div>
        <div class="grid-container">
          <div class="grid-item">
            <img class="img1" src="@/assets/formpicture.png" alt="Vue Form">
            <br>
            <a class="link" href="https://web-form-vue-lake.vercel.app/">Web Form app (Vue)</a>
          </div>
          <div class="grid-item">
            <img class="img1" src="@/assets/yetiii.png" alt="Weather Yeti">
            <br>
            <a class="link" href="https://cerovina.github.io/Weather-Yeti/">Weather Yeti app (React)</a>
          </div>
        </div>
      </section>
    </div>
  </template>

<style scoped>

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

</style>