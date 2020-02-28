<template functional>
  <a :href="props.href" :target="`${props.newTab ? '_blank' : ''}`">
    <i :class="props.icon"></i>
  </a>
</template>

<script>
export default {
  // eslint-disable-next-line vue/name-property-casing
  name: 'icon-button',
  functional: true,
  props: {
    href: {
      type: String,
      default: '#'
    },
    icon: {
      type: String,
      default: 'fas fa-atom'
    },
    newTab: {
      type: Boolean,
      default: false
    },

    fill: {
      type: String,
      default: ''
    }
  }
}
</script>

<style lang="scss" scoped>
$grainer-color: #02f6b6;

a {
  margin-bottom: 4px;
  padding: 2px 8px;
  color: black;
  background-color: $grainer-color;
  border: 1px solid $grainer-color;
  border-radius: 7px 0px 7px 7px;
}
</style>
