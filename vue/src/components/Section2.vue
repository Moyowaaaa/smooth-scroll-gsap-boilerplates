<script setup lang="ts">

import { ref, onMounted, onUnmounted,watchEffect } from 'vue'
import gsap from "gsap";
import ScrollTrigger from "gsap/ScrollTrigger";
gsap.registerPlugin(ScrollTrigger)

// onMounted(() => {
//   const section2tl = gsap.timeline({
//     scrollTrigger: {
//       trigger:'#section2',
//       start: "top center",
//       end: "top +=10",
//     }
//   })
//   section2tl.to('#section2',{backgroundColor:'blue',color:'white',duration:1.2})
// })

onMounted(() => {
  const ctx = gsap.context(() => {
    const sectionTwoTl = gsap.timeline({
      scrollTrigger:{
        trigger:'#section2',
        start: "top center",
      end: "top +=10",
      // markers:true,
      scrub: 0.7,
      }
    })
    sectionTwoTl.fromTo('#box',{opacity:0},{ y: 0, opacity: 1, duration:1.5, clipPath: "polygon(0 100%, 100% 100%, 100% 0, 0 0)", ease:"power3.inOut" },'<0.1')

return () => ctx.revert()
  })

 
})

</script>

<template >
    <section  id="section2"  data-scroll-section>
        <p>Hola</p>
    
        <div class="box-container">
        <div class="box1" id="box"></div>


<!-- <div class="box2"></div> -->
      </div>
     
    </section>
</template>



<style scoped>
section{
    height: 100vh;
    width: 100%;
    background-color: white;
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column;
}
.box-container{
  display: flex;
  width: 100%;
  
}

.box1{
  
  height: 20rem;
  width: 20rem;
  margin: 0 auto;
  background-color: red;
}

.box2{
  
  height: 300px;
  width: 30%;
  background-color: teal;
}

</style>