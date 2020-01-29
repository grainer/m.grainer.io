<template>
  <div class="w-full flex flex-row">
    <div v-show="$route.hash === '#home'" class="fixed inset-0 w-screen h-screen">
      <video class="w-full bg-green-dark" autoplay="true" loop="true">
        <source src="@/assets/vid/seed-m-cp.webm" type="video/webm" />

        <source src="@/assets/vid/seed-m-cp.mp4" type="video/mp4" />
      </video>
    </div>
    <div class="w-1/2 flex justify-center align-middle z-10 bottom-0 mx-auto h-screen">
      <h1 class="font-h h-1/2 my-auto start-line text-5xl">
        Everything Starts With an
        <span class="idea px-4">idea</span>
      </h1>
    </div>
  </div>
</template>

<script>
export default {
  //
}
</script>

<style>
.start-line {
  font-weight: bold;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.2;
  letter-spacing: 2.5px;
  text-align: left;
}
.idea {
  color: #011b14;
  background-color: #02f6b6;
}
</style>
