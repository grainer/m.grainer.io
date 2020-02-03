<template functional>
  <a class="techholder" :href="props.link">
    <center>
      <img :src="props.icon" />
      <h1 class="my-4 md:mx-8">{{ props.name }}</h1>
    </center>
  </a>
</template>

<script>
export default {
  functional: true,
  props: {
    name: {
      type: String,
      default: 'No Title'
    },
    icon: {
      type: String,
      default: '@/assets/img/nem.svg'
    },
    link: {
      type: String,
      default: 'https://nem.io'
    }
  }
}
</script>

<style lang="scss" scoped>
@import '../assets/css/grainer';

.techholder {
  max-width: 25vw;
  padding: 1rem 1rem 1rem 1rem;

  img {
    filter: sepia(1) contrast(35%) hue-rotate(69deg);
    -webkit-filter: sepia(1) contrast(35%) hue-rotate(69deg);
  }

  h1 {
    font-family: 'Taviraj', serif;
  }
}
</style>
