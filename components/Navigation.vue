<template>
  <nav :class="`navbar ${!transparent ? 'transparent' : ''} ${addclass}`">
    <a href="https://m.grainer.io"><img :src="require('@/static/logo@2x.png')"/></a>
    <div class="header-buttons">
      <icon-button href="https://api.whatsapp.com/send?phone=60122441566&text=&source=&data=" icon="fab fa-whatsapp"></icon-button>
      <button :class="`hamburger hamburger--minus ${isOpen ? 'is-active' : ''}`" type="button" @click="toggle">
        <span class="hamburger-box">
          <span class="hamburger-inner"></span>
        </span>
      </button>
    </div>
    <!-- the menu box that will show on user click -->
    <div v-if="isOpen" class="content">
      <ul>
        <li v-for="({ link, title }, index) in menuItems" :key="index">
          <!-- <nuxt-link :to="link">{{ title }}</nuxt-link> -->
          <a :href="link">{{ title }}</a>
          <!-- <a @click="goto(link)">{{ title }}</a> -->
        </li>
      </ul>
    </div>
  </nav>
</template>

<script>
import IconButton from './IconButton.vue'

export default {
  name: 'Navigation',
  components: {
    IconButton
  },
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
          link: 'https://m.grainer.io/about',
          title: 'About Us'
        },
        {
          link: 'https://m.grainer.io/career',
          title: 'Career'
        },
        {
          link: 'https://m.grainer.io/contact',
          title: 'Contact Us'
        }
      ]
    }
  },
  methods: {
    toggle() {
      this.isOpen = !this.isOpen
    },
    goto(link) {
      this.$router.push(`${link}`)
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
  align-items: center;
  flex-wrap: wrap;
  justify-content: space-between;

  &:not(.transparent) {
    background-color: rgba($bg-color, 0.8);
    backdrop-filter: blur(4px);
  }

  img {
    width: 45vw;
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

.header-buttons {
  display: flex;
  align-items: center;
  a {
    margin-bottom: 4px;
    padding: 2px 8px;
    color: black;
    background-color: #02f6b6;
    border-radius: 7px 0px 7px 7px;
  }
}
</style>
