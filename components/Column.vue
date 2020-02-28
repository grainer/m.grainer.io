<template functional>
  <div :id="id" :class="`flex items-${props.align} justify-${props.justify} w-${props.width} `">
    <slot></slot>
  </div>
</template>

<script>
export default {
  name: 'Column',
  functional: true,
  props: {
    id: {
      type: String,
      default: null
    },
    /* https://tailwindcss.com/docs/align-items/#app */
    align: {
      type: String,
      default: 'center'
    },
    /* https://tailwindcss.com/docs/justify-items/#app */
    justify: {
      type: String,
      default: null
    },
    /* https://tailwindcss.com/docs/width/#app */
    width: {
      type: String,
      default: ''
    },
    /* any tailwindcss class that works with flex */
    addclass: {
      type: String,
      default: null
    }
  }
}
</script>
