<template functional>
  <div class="flex h-full pr-20 flex-col justify-center">
    <img :src="require('@/assets/img/illustration-1-2.png')" />
    <textholder
      title="STARTING FROM SCRATCH?"
    >Our highly skilled developers can convert your big ideas into reliable and robust code. Paired with expert designers, we can guarantee your final product will be seamless, intuitive, and engaging.</textholder>
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
