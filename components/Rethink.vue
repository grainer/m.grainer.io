<template functional>
  <div class="flex h-full pr-20 flex-col justify-center">
    <img :src="require('@/assets/img/illustration-2-2.png')" />
    <textholder
      title="RETHINKING YOUR SOLUTION?"
    >Our consulting and development teams analyze your existing system and recommend solutions that would make your business relevant to the ever-changing industry standards.</textholder>
    <gbutton addclass="mt-8 mr-24">Talk To Us</gbutton>
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
