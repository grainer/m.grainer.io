<template>
  <div class="h-screen px-10">
    <img :src="require('@/assets/img/mapbox.png')" class="mapbox" />
    <contact></contact>
  </div>
</template>

<script>
import Contact from '@/components/Contact'

export default {
  components: {
    contact: Contact
  }
}
</script>

<style lang="scss" scoped>
.mapbox {
  position: fixed;
  bottom: 0%;
  left: 0px;
  width: 100vw;
  z-index: -1;
  opacity: 0.3;
}
</style>
