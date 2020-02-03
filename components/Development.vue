<template functional>
  <div class="flex flex-col justify-center pt-12 pr-24 help-container">
    <h1 class="help-title mb-8">
      HOW CAN WE
      HELP YOU?
    </h1>
    <textholder title="DEVELOPMENT">
      Our dedicated team of technology experts partner with you and usher you through every step of the way to translate your ideas into robust solutions.
      Using cutting edge technologies and best practices, we aim to develop solutions that are scalable, secure, and maintainable, putting you and your company at the forefront of your industry.
    </textholder>
    <gbutton addclass="mt-8 mr-20">Talk To Us</gbutton>
  </div>
</template>

<script>
import Vue from 'vue'
import Textholder from '@/components/Textholder.vue'
import GButton from '@/components/GButton'

Vue.component('textholder', Textholder)
Vue.component('gbutton', GButton)

export default {
  functional: true
}
</script>

<style lang="scss" scoped>
@import '../assets/css/grainer';

.help-container {
  height: 100%;
}

.help-title {
  font-family: Roboto;
  @include help-title;
}
</style>
