<template>
  <div class="contactWrap">
      <div class="contact">
        <h1 class="heading">Contact</h1>
          </div>
    <section>
      <div class="end">
        <p>
          📧<span class="yellow i"> Email:</span><br>cerovina1997@gmail.com
          <br>
          <br>
          🌐<span class="yellow i"> LinkedIn:</span><br><a class="link" href="https://linkedin.com/in/cerovina">Connect with me</a>
          <br>       
        </p>
      </div>
      <div class="grid-item">
            <img class="img2" src="@/assets/mail1.png" alt="Mailbox Image">
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

  .contactWrap {
  background-color: #0F0225;
}
  .end {
      margin-top: 35px;
    }

  .img2 {
    margin-top: 35px;
    width: 9.2%;
  }

  .i {
    font-style: italic;
  }

  @media (max-width: 767px) {
  p {
    width: 75%;
  }

  h1{
    margin: auto;
  }

  .img2 {
    margin-top: 35px;
    width: 30%;
  }
}
  </style>