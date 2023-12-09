<script setup lang="ts">
  import { onMounted, onUpdated } from "vue";
  import { gsap } from "gsap";
  import { ScrollTrigger } from "gsap/ScrollTrigger";

  gsap.registerPlugin(ScrollTrigger);


  const animate = () => {

  };

  onMounted(animate);
  onUpdated(animate);
</script>

<template>
  <em>sliding animation</em>
</template>
