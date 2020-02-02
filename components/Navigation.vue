<template>
  <nav :class="`navbar ${!isOpen && transparent ? 'transparent' : ''} ${addclass}`">
    <img :src="require('@/static/logo@2x.png')" />
    <button
      :class="`hamburger hamburger--minus ${isOpen ? 'is-active' : ''}`"
      type="button"
      @click="toggle"
    >
      <span class="hamburger-box">
        <span class="hamburger-inner"></span>
      </span>
    </button>
    <!-- the menu box that will show on user click -->
    <div v-if="isOpen" class="content">
      <ul>
        <li v-for="({link, title}, index) in menuItems" :key="index">
          <!-- <nuxt-link :to="link">{{ title }}</nuxt-link> -->
          <a :href="link">{{ title }}</a>
        </li>
      </ul>
    </div>
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
      isOpen: false,
      menuItems: [
        {
          link: '/',
          title: 'Home'
        },
        {
          link: 'about',
          title: 'About Us'
        },
        {
          link: 'career',
          title: 'Career'
        },
        {
          link: '/contact',
          title: 'Contact Us'
        }
      ]
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
  z-index: 101;
  top: 0%;
  width: 100vw;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;

  &:not(.transparent) {
    background-color: rgba($bg-color, 0.8);
    backdrop-filter: blur(4px);
  }

  img {
    width: 200px;
  }

  .transparent {
    background-color: rgba(0, 0, 0, 0);
  }
}

.content {
  $darkened: darken($grainer-color, 10);
  width: 100vw;
  padding: 1rem 2rem 1rem 2rem;
  // border-top: 2px solid $darkened;
  // border-bottom: 2px solid $darkened;

  ul {
    font-size: 1.2rem;
    font-family: 'Taviraj';
    line-height: 2.5rem;
    text-align: center;

    li {
      &:not(:last-child) {
        border-bottom: 0.5px solid $grainer-color;
      }
      /* highlight on click */
      &:active {
        background-color: darken($grainer-color, 2);
        background-size: 100%;
        transition: background 0s;
      }
    }
  }
}
</style>
