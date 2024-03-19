<template>
  <div id="particles-js"></div>
</template>

<script>
import particlesJSON from '@/utils/particle.json'
export default {
  name: 'ParticlesComponent',
  mounted() {
    // Load particles.js lib
    const particlesScript = document.createElement('script')
    particlesScript.src = 'http://cdn.jsdelivr.net/particles.js/2.0.0/particles.min.js'
    document.head.appendChild(particlesScript)

    // Initialize particles.js
    particlesScript.onload = () => {
      particlesJS('particles-js', particlesJSON)
    }
  }
}
</script>

<style scoped>
#particles-js {
  position: absolute;
  width: 100%;
  height: 100%;
  top: 0;
  right: 0;
  background-color: transparent;
  overflow: hidden;
}
</style>
