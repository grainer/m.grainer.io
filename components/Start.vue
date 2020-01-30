<template>
  <div class="container">
    <video autoplay muted loop>
      <source :src="require('@/assets/vid/seed.mp4')" type="video/mp4" />
    </video>

    <h1>
      Everything Starts With an
      <span class="idea px-4">idea</span>
    </h1>
  </div>
</template>

<script>
export default {
  //
}
</script>
<style lang="scss" scoped>
.container {
  video {
    position: absolute;
    left: 0px;
  }

  h1 {
    position: relative;
  }
}
</style>
