<template functional>
  <div :class="`textholder ${props.addclass}`">
    <h1 v-if="props.title" class="text-3xl md:text-5xl">{{ props.title }}</h1>
    <h3 v-if="props.author" class="text-base md:text-xl">anjeng {{ props.author }}</h3>
    <div class="w-16 h-2 bg-gr-green-light mt-1 md:h-3 md:mt-2 mb-2 md:mb-4"></div>
    <p v-if="slots().default" class="text-base">
      <slot></slot>
    </p>
    <a
      v-if="props.link"
      :href="props.link.href"
      class="text-3xl md:text-5xl interactive"
      target="_blank"
    >{{ props.link.title }}</a>
  </div>
</template>

<script>
export default {
  name: 'Textholder',
  functional: true,
  props: {
    addclass: {
      type: String,
      default: 'w-full'
    },
    title: {
      type: String,
      default: null
    },
    link: {
      type: Object,
      default: null
    }
  }
}
</script>
<style lang="scss" scoped>
@import '../assets/css/grainer';
// font sizes are set by tailwind
.textholder {
  text-align: left;
  color: #ffffff;

  h1 {
    font-family: Roboto;
    line-height: 1.2;
    font-weight: bold;
    letter-spacing: 0.15rem;
    color: #ffffff;
  }

  p {
    font-family: Glegoo;
    line-height: 1.5;
  }

  a {
    font-family: Taviraj;
    font-weight: normal;
    font-style: normal;
    text-align: left;
    color: #02f6b6;
  }

  h3 {
    font-family: Taviraj;
    letter-spacing: 1.8px;
    padding: 1rem 0 1rem 0;
  }
}
</style>
