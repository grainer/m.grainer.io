<template functional>
  <div class="flex flex-col justify-center pt-12 pr-24 help-container">
    <h1 class="help-title mb-8">
      HOW CAN WE
      HELP YOU?
    </h1>
    <textholder title="INNOVATION HUB">
      We constantly research and develop solutions for the right use case and corresponding market. We are passionate about emerging technologies in the areas of blockchain, artificial intelligence (AI), machine learning, advanced security solutions, data analytics, and the Internet of Things.
      Grainer is always on the lookout for startups in the ideation stage for incubation.
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
