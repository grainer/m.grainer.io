<template functional>
  <div class="container">
    <div>
      <h1>
        Everything starts with an
        <span class="idea px-4">idea</span>
      </h1>
    </div>
    <video v-show="props.showvideo" class="bgvideo" autoplay muted loop>
      <source :src="require('@/assets/vid/seed.mp4')" type="video/mp4" />
    </video>
  </div>
</template>

<script>
export default {
  functional: true,
  props: {
    showvideo: {
      type: Boolean,
      default: false
    }
  }
}
</script>
<style lang="scss" scoped>
@import '../assets/css/grainer';

.container {
  display: flex;
  height: 100%;
  align-content: center;
  align-items: center;

  .bgvideo {
    width: 100vw;
    position: fixed;
    top: 0;
    right: 0;
    bottom: 0;
    left: 0;
    overflow: hidden;
    z-index: 0;
  }

  h1 {
    padding: 0 30% 0 0;
    position: relative;
    z-index: 10;
    font-family: Roboto;
    font-size: 3rem;
    font-weight: bold;
    line-height: 1.42;
    letter-spacing: 1.06px;
  }

  .idea {
    @include idea;
  }
}
</style>
