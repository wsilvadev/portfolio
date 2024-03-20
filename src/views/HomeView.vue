<script setup lang="ts">
import Particles from '@/components/Particles.vue'
</script>

<template>
  <main>
    <Particles />
    <div class="img-container">
      <img src="../assets/profile.png" class="profile-img" />
    </div>
    <div class="title-decription">
      <div class="title-decription-inner">
        <div class="title-decription-name">
          <div class="title-decription-name-inner">Willian Simões</div>
        </div>
        <div class="mozart">
          <div class="mozart-inner">Software Developer <span>(</span> Front end <span>)</span></div>
        </div>
      </div>
    </div>
  </main>
</template>

<style scoped>
span {
  color: #a5086b;
}
.title-description {
  position: absolute;
  top: 30%;
  left: 200px; /* Ajuste conforme necessário */
  transform: translateX(-50%);
  color: blanchedalmond;
  font-family: 'Ysabeau Infant', sans-serif;
  font-weight: 100;
  font-style: normal;
  white-space: nowrap; /* Evita que o texto quebre em várias linhas */
  z-index: 2;
}

.title-description-inner {
  display: inline-block;
}

@keyframes text-clip {
  from {
    clip-path: polygon(0% 100%, 100% 100%, 100% 100%, 0% 100%);
  }

  to {
    clip-path: polygon(0 0, 100% 0, 100% 100%, 0 100%);
  }
}

@keyframes outer-left {
  from {
    transform: translateX(50%);
  }

  to {
    transform: none;
  }
}

@keyframes inner-left {
  from {
    transform: translateX(-50%);
  }

  to {
    transform: none;
  }
}

.title-decription-name,
.mozart {
  animation: outer-left 1s 1s cubic-bezier(0.5, 0, 0.1, 1) both;
}

.title-decription-inner {
  display: inline-block;
  font-size: 30px;
  animation: inner-left 1s 1s ease both;
}

.title-decription-name-inner {
  display: inline-block;
  font-size: 40px;
  animation: inner-left 1s 1s ease both, text-clip 1s 0s cubic-bezier(0.5, 0, 0.1, 1) both;
}

.mozart-inner {
  animation: text-clip 1s 0s cubic-bezier(0.5, 0, 0.1, 1) both;
}

.title-decription {
  animation: outer-left 1s 1s ease both;
}

.title-decription-name-inner {
  display: inline-block;
}

.mozart {
  display: inline-block;
}

.img-container {
  position: absolute;
  right: 70px;
  bottom: 0;
  z-index: 10;
}

.img-container::before {
  content: '';
  position: absolute;
  width: 100%;
  height: 4px;
  background-color: #51ff97;
  transform-origin: center center;
  transform: scaleX(0);

  animation: line-animation 3s ease forwards;
}

.profile-img {
  width: 400px;
  bottom: 0;
  right: 70px;
  z-index: 10;
  animation: clip-path-reveal-1 3s ease forwards;
}

@keyframes line-animation {
  0% {
    transform: scaleX(0);
  }

  15% {
    transform: scaleX(0);
  }

  20%,
  25% {
    transform: scaleX(1);
    top: calc(100% - 2px);
  }

  50% {
    transform: scaleX(1);
    top: 0px;
  }

  70% {
    transform: scaleX(0.2);
    top: 0px;
  }

  80%,
  100% {
    transform: scaleX(0);
    top: 0px;
  }
}

@keyframes clip-path-reveal-1 {
  0%,
  25% {
    clip-path: polygon(0 100%, 100% 100%, 100% 100%, 0% 100%);
  }

  50% {
    clip-path: polygon(0 0, 100% 0, 100% 100%, 0% 100%);
  }
}

@media (max-width: 750px) {
  .profile-img {
    width: 200px;
    right: 10px;
    z-index: 10;
  }

  .title-decription {
    margin: 10px;
    top: 10%;
    font-size: 10vw;
  }
}
.title {
  position: absolute;
  top: 20px;
  left: 20%;
  background-color: red;
}
</style>
