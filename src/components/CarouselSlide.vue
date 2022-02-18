<template>
  <transition >
  

    <div v-show="visibleSlide === index" class="carousel-slide">
      <slot></slot>
    </div>


  </transition>
</template>

<script>
export default {
  props: ["visibleSlide", "index"],
  data() {
    return {};
  }
};
</script>

<style>

.carousel-slide{

  top:0;
  left:0;
  right:0;
  bottom:0;

}
.left-enter-active{

animation:leftEnterAnimation 0.4s ease-in-out;

}
.left-leave-active {

animation:leftLeaveAnimation 0.4s ease-in-out;

}
@keyFrames leftEnterAnimation {

  from{ transform :translateX(100%);}
  to{ transform:translateX(0);}

}
@keyFrames leftLeaveAnimation {
  from{ transform :translateX(0);}
  to{ transform:translateX(-100%);}
  
}


</style>
