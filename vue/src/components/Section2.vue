<template>
  <div ref="element" class="intersection-target">
    
    <h1 id="isVisible">I'm in view bro </h1>
  </div>
</template>

<script setup lang="ts">
import gsap from 'gsap';
import { ref, onMounted, onUnmounted,watchEffect,watch,inject } from 'vue';
import {useIntersectionObserver} from '../composables/useIntersectionObserver'

const ispageVisible = ref<boolean>()
const isVisible = ref<boolean>()

const element = ref<HTMLDivElement | null>(null);

// onMounted(() => {
//   element.value = document.querySelector('.intersection-target')
//   console.log(element.value)
// })

// watchEffect(() => {
//   console.log(element.value)
// })

const isIntersecting = useIntersectionObserver(element.value,0.12)


console.log({isIntersecting})






  


// const observer = new IntersectionObserver(
//   (entries) => {
//     entries.forEach((entry) => {
//       if (entry.isIntersecting) {
//         console.log('Element is in view');
//         isVisible.value = true
//       } else {
//         console.log('Element is out of view');
//         isVisible.value = false
//       }
//     });
//   },
//   {
//     root: null,
//     rootMargin: '0px',
//     threshold: 0.1,
//   }
// );

// onMounted(() => {
//   observer.observe(element.value!);
// });

// onUnmounted(() => {
//   observer.disconnect();
// });

// watchEffect(() => {
//   console.log(isVisible.value)
//   if(isVisible) {
//     gsap.from('#isVisible', {
//       opacity:0,
//       duration:1,
//       y:200
//     })
//   }

// })


// if(ispageVisible){
//     gsap.from('#isVisible', {
//       opacity:0,
//       duration:1,
//       y:200
//     })
//   }




</script>

<style scoped>
.intersection-target {
  height: 100vh;
}
</style>