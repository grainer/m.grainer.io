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
  </div>
</template>

<script>
// eslint-disable-next-line no-unused-vars
import GButton from '@/components/GButton'
export default {
  funtional: true,
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
  padding: 2rem 3rem 2rem 0rem;
  align-items: center;
  display: flex;

  h1 {
    font-size: 2rem;
    font-weight: bold;
    line-height: 1.62;
    letter-spacing: 0.65px;
    text-align: left;
    color: #ffffff;
    z-index: 1;
  }
}
.idea {
  @include idea;
}
</style>
