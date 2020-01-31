<template functional>
  <nav class="nav nav--desta">
    <svg class="hidden">
      <defs>
        <symbol id="icon-triangle" viewBox="0 0 24 24">
          <title>triangle</title>
          <path
            d="M4.5,19.8C4.5,19.8,4.5,19.8,4.5,19.8V4.2c0-0.3,0.2-0.5,0.4-0.7c0.2-0.1,0.5-0.1,0.8,0l13.5,7.8c0.2,0.1,0.4,0.4,0.4,0.7c0,0.3-0.2,0.5-0.4,0.7L5.7,20.4c-0.1,0.1-0.3,0.1-0.5,0.1C4.8,20.6,4.5,20.2,4.5,19.8z M6,5.6v12.8L17.2,12L6,5.6z"
          />
        </symbol>
      </defs>
    </svg>
    <a
      v-for="number in props.totalpages"
      :key="number"
      :class="`nav__item ${number === props.currentpage ? 'nav__item--current' : ''}`"
      :aria-label="`Page ${number}`"
      :href="`#page${number}`"
    >
      <svg class="nav__icon">
        <use xlink:href="#icon-triangle" />
      </svg>
      <span class="nav__item-title">{{ number }}</span>
    </a>
  </nav>
</template>

<script>
export default {
  functional: true,
  props: {
    totalpages: {
      type: Number,
      default: 6
    },
    currentpage: {
      type: Number,
      default: 1
    }
  }
}
</script>

<style lang="scss" scoped>
@import '../assets/css/grainer';

.nav {
  position: relative;
  width: 8em;
  z-index: 100;
  margin: 0 0 0 3em;

  .nav__item {
    line-height: 1;
    position: relative;
    display: block;
    margin: 0;
    padding: 0;
    letter-spacing: 0;
    border: 0;
    background: none;
    color: darken($grainer-color, 30%);
    -webkit-tap-highlight-color: rgba(0, 0, 0, 0);

    :focus {
      outline: none;
    }
  }
}

/*
  the styling for the triangles
*/
.nav--desta .nav__item {
  width: 5em;
  height: 3.5em;
}

.nav--desta .nav__icon {
  position: absolute;
  top: 0.2em;
  left: 0;
  width: 1.5em;
  height: 1.5em;
  -webkit-transform: rotate3d(0, 0, 1, -90deg);
  transform: rotate3d(0, 0, 1, -90deg);
  -webkit-transition: -webkit-transform 0.5s, fill 0.5s;
  transition: transform 0.5s, fill 0.5s;
  -webkit-transition-timing-function: cubic-bezier(0.2, 1, 0.3, 1);
  transition-timing-function: cubic-bezier(0.2, 1, 0.3, 1);
  fill: currentColor;
}

.nav--desta .nav__item--current .nav__icon {
  -webkit-transform: rotate3d(0, 0, 1, 0deg);
  transform: rotate3d(0, 0, 1, 0deg);
  fill: $grainer-color;
}

.nav--desta .nav__item-title {
  font-family: 'Roboto Condensed', sans-serif;
  line-height: 2;
  display: block;
  white-space: nowrap;
  letter-spacing: 2px;
  text-transform: uppercase;
  opacity: 0;
  color: $grainer-color;
  -webkit-transform: translate3d(-10px, -10px, 0);
  transform: translate3d(-10px, -10px, 0);
  -webkit-transition: -webkit-transform 0.5s, opacity 0.5s;
  transition: transform 0.5s, opacity 0.5s;
  -webkit-transition-timing-function: cubic-bezier(0.2, 1, 0.3, 1);
  transition-timing-function: cubic-bezier(0.2, 1, 0.3, 1);
}

.nav--desta .nav__item--current .nav__item-title {
  opacity: 1;
  -webkit-transform: translate3d(0, 0, 0);
  transform: translate3d(0, 0, 0);
}
</style>
