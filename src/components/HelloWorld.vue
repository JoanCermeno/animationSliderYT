<script setup>
const nombresImagenes = [
  "avelina.webp",
  "genica.webp",
  "gomby.webp",
  "marca_puig.webp",
  "mondelez-logo.webp",
  "mortiz.webp",
  "natulac.webp",
  "paveca.webp",
  "pepsico_l.webp",
  "ponce&benzo.webp",
];
</script>

<template>
  <section class="w-full p-5 flex flex-row relative">
    <div class="w-full p-2 flex flex-row justify-between flex-shrink-0 slider">
      <img
        v-for="imagen in nombresImagenes"
        :src="`/${imagen}`"
        :alt="`${imagen}`"
      />
    </div>

    <div class="w-full p-2 flex flex-row justify-between flex-shrink-0 slider">
      <img
        v-for="imagen in nombresImagenes"
        :src="`/${imagen}`"
        :alt="`${imagen}`"
      />
    </div>
  </section>
</template>

<style scoped>
img {
  width: 100px;
  height: 100px;
  object-fit: contain;
}
.slider {
  animation: 35s mover linear infinite;
}

section:hover .slider {
  animation-play-state: paused;
  cursor: pointer;
}

section::before {
  content: "";
  width: 400px;
  height: 110px;
  position: absolute;
  background: rgb(255, 255, 255);
  background: linear-gradient(
    90deg,
    rgba(255, 255, 255, 1) 0%,
    rgba(255, 0, 0, 0) 100%
  );
  z-index: 10;
  left: 0;
}

section::after {
  content: "";
  width: 400px;
  height: 110px;
  position: absolute;
  background: rgb(255, 255, 255);
  background: linear-gradient(
    250deg,
    rgba(255, 255, 255) 0%,
    rgba(255, 0, 0, 0) 100%
  );
  z-index: 10;
  right: 0;
}
@keyframes mover {
  0% {
    transform: translateX(0);
  }
  100% {
    transform: translateX(-100%);
  }
}
</style>
