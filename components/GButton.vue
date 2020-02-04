<template functional>
  <button
    :class="`px-${props.padx} py-${props.pady} rounded-lg rounded-tr-none border-gr-green-light border-2 font-sh outline-none slide interactive ${props.addclass}`"
    @click="props.onclick"
  >
    <slot></slot>
  </button>
</template>

<script>
export default {
  functional: true,
  props: {
    onclick: {
      type: Function,
      default: () => {
        console.log('i is clicked wkwkwk')
      }
    },
    pady: {
      type: String,
      default: '2'
    },
    padx: {
      type: String,
      default: '2'
    },
    addclass: {
      type: String,
      default: ''
    }
  }
}
</script>
