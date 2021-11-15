<template>
  <div class="about">
    <transition 
      appear       
      @before-enter="beforeEnter"
      @enter="enter"  
      @after-enter="afterEnter"         
    >
      <h1>About GSAP</h1>
    </transition>
    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Cum aperiam officia possimus delectus inventore quod quisquam culpa voluptas iusto, quae maiores quo dolorum, corporis laboriosam a dolore consequatur assumenda nam!</p>
    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Cum aperiam officia possimus delectus inventore quod quisquam culpa voluptas iusto, quae maiores quo dolorum, corporis laboriosam a dolore consequatur assumenda nam!</p>
    
  </div>
</template>

<script>
import { ref } from 'vue'
import gsap from 'gsap'
export default {
  setup() {    

    const beforeEnter = (el) => {        
        el.style.transform = 'translateY(-60px)'
        el.style.opacity = 0
    }
    const enter = (el, done) => {         
      gsap.to(el, {
          duration: 1,
          y:0,
          opacity: 1,
          ease: 'bounce.out',
          onComplete: done
      })
    }

    const afterEnter = () => {
        console.log('after Enter')
    }
    
    return {beforeEnter, enter, afterEnter}
  }
}
</script>

<style>  

</style>