<template>
  <nav :class="`navbar ${!isOpen && transparent ? 'transparent' : ''} ${addclass}`">
    <img :src="require('@/static/logo@2x.png')" />
    <button :class="`hamburger hamburger--minus ${isOpen ? 'is-active' : ''}`" type="button" @click="toggle">
      <span class="hamburger-box">
        <span class="hamburger-inner"></span>
      </span>
    </button>
  </nav>
</template>

<script>
export default {
  name: 'Navigation',
  props: {
    addclass: {
      type: String,
      default: ''
    },
    transparent: {
      type: Boolean,
      default: true
    }
  },
  data() {
    return {
      isOpen: false
    }
  },
  methods: {
    toggle() {
      this.isOpen = !this.isOpen
    }
  }
}
</script>

<style lang="scss" scoped>
@import '../assets/css/hamburger.scss';

.navbar {
  position: fixed;
  z-index: 100;
  top: 0%;
  width: 100vw;
  display: flex;
  justify-content: space-between;

  &:not(.transparent) {
    background-color: rgba($bg-color, 0.8);
    backdrop-filter: blur(6px);
  }

  img {
    width: 200px;
  }

  .transparent {
    background-color: rgba(0, 0, 0, 0);
  }
}
</style>
