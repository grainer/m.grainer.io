<template functional>
  <div class="flex flex-col justify-center pt-12 pr-24 help-container">
    <h1 class="help-title mb-8">
      HOW CAN WE
      HELP YOU?
    </h1>
    <textholder title="CONSULTANCY">
      We offer consulting and technology implementation services to businesses that want to re-define their customer success stories through digital transformation.
      Our consulting team helps deliver remarkable enterprise architecture designs, business plan development, proof of concept, process automation and more. We help you make sound decisions and evaluate the right solutions for your business.
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
