<template functional>
  <a :href="props.href" class="join interactive" target="_blank">
    <h1>join the <br />grainer family</h1>
    <i class="fas fa-plus-circle"></i>
  </a>
</template>

<script>
export default {
  name: 'Joincard',
  functional: true,
  props: {
    href: {
      type: String,
      default: '#'
    }
  }
}
</script>

<style lang="scss" scoped>
.join {
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: space-evenly;
  width: 100%;
  padding: 1rem 0;
  color: #02f6b6;
  border: solid 2px #02f6b6;
  font-family: Roboto;
  font-size: 1.5rem;
  font-weight: bold;
  line-height: 1.2;
  text-align: left;
  text-transform: uppercase;

  i {
    font-size: 2.5rem;
  }

  &:hover {
    color: black;
    background-color: #02f6b6;
  }
}
</style>
