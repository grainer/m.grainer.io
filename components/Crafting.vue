<template functional>
  <div id="crafting">
    <div v-if="props.showimage" id="crafting-bg"></div>
    <h1>
      Crafting robust
      <br />enterprise
      <br />
      <span class="idea px-2">IT Solutions</span>
      is
      <br />our commitment and passion
    </h1>
    <div class="w-16 h-2 bg-gr-green-light mt-1 md:h-3 md:mt-2 mb-2 md:mb-4"></div>
    <h2>We are an IT company with expertise in Blockchain and Artificial Intelligence.</h2>
  </div>
</template>

<script>
import Vue from 'vue'
import GButton from '@/components/GButton'
Vue.component('gbutton', GButton)

export default {
  functional: true,
  props: {
    showimage: {
      type: Boolean,
      default: false
    }
  }
}
</script>

<style lang="scss" scoped>
@import '../assets/css/grainer';

#crafting-bg {
  position: fixed;
  top: 0%;
  left: 0%;
  z-index: 0;
  width: 100vw;
  height: 100vh;
  opacity: 0.1;
  background-image: url('../assets/img/bio.png');
  background-size: cover;
  -ms-background-size: cover;
  -o-background-size: cover;
  -moz-background-size: cover;
  -webkit-background-size: cover;
  background-repeat: no-repeat;
  background-attachment: fixed;
  background-position: center;
}

#crafting {
  height: 100%;
  padding: 2rem 5rem 2rem 0rem;
  justify-content: center;
  align-content: center;
  display: flex;
  flex-direction: column;
  font-family: 'Roboto', sans-serif;

  h1 {
    font-size: 2.1rem;
    font-weight: bold;
    line-height: 1.5;
    letter-spacing: 0.65px;
    text-align: left;
    color: #ffffff;
    z-index: 1;
  }

  h2 {
    font-family: Glegoo;
    font-size: 1rem;
    font-weight: bold;
    line-height: 1.82;
    text-align: left;
  }

  .gbutton {
    margin-top: 1rem;
    width: 50%;
  }
}
.idea {
  @include idea;
}
</style>
