<template functional>
  <div class="flex flex-col h-full justify-center pr-8">
    <img v-show="props.showimage" :src="require('@/assets/img/mapbox.png')" class="mapbox" />
    <subscribe addclass="w-full my-8"></subscribe>
    <textholder title="CALL" :link="{title: '+6012 244 1566', href:'https://wa.me/60122441566'}"></textholder>
    <textholder title="EMAIL" :link="{title: 'info@grainer.io', href:'mailto:info@grainer.io'}"></textholder>
    <h1 class="address">
      Tier 2 The Warehouse Wisma Commercedotcom
      Jalan Tandang 51/204 46050
      Petaling Jaya, Selangor, Malaysia
    </h1>
  </div>
</template>

<script>
import Vue from 'vue'
import Textholder from '@/components/Textholder.vue'
import Subscribe from '@/components/Subscribe.vue'

Vue.component('textholder', Textholder)
Vue.component('subscribe', Subscribe)

export default {
  functional: true
}
</script>

<style lang="scss" scoped>
@import '../assets/css/grainer';

.address {
  font-size: 1rem;
  font-family: Taviraj;
  line-height: 1.82;
  text-align: left;
  color: $grainer-color;
  padding-top: 2rem;
}

.mapbox {
  position: fixed;
  bottom: 0%;
  left: 0px;
  width: 100vw;
  z-index: -1;
  opacity: 0.3;
}
</style>
