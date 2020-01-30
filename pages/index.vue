<template>
  <div id="index">
    <div id="index-nav" class="nav--desta">
      <!-- the trinagle dot pagination -->
      <pagination :totalpages="noOfPages" :currentpage="activePage"></pagination>
      <!--
      add your pages here. wrap it in a
      <div data-anchor="page{ number }}">{ your component }</div>
      -->
    </div>
    <div id="index-content">
      <div data-anchor="page1">
        <start :showvideo="$route.hash === '#page1'"></start>
      </div>
      <div data-anchor="page2">
        <crafting></crafting>
      </div>
      <div data-anchor="page3">
        <help></help>
      </div>
      <div data-anchor="page4">
        <start></start>
      </div>
    </div>
    <next :onclick="() => pages.next()"></next>
  </div>
</template>

<script>
// eslint-disable-next-line no-unused-vars
import Pageable from 'pageable'
import Start from '@/components/Start'
import Crafting from '@/components/Crafting'
import Help from '@/components/Help'
import Pagination from '@/components/Pagination'
import Next from '@/components/Next'
export default {
  components: {
    // eslint-disable-next-line vue/no-unused-components
    start: Start,
    pagination: Pagination,
    next: Next,
    // eslint-disable-next-line vue/no-unused-components
    crafting: Crafting,
    help: Help
  },
  data() {
    return {
      pages: null,
      noOfPages: 6,
      activePage: 1,
      showVideo: true
    }
  },
  mounted() {
    // get the element that holds the pages
    const contentHolder = document.getElementById('index-content')
    this.noOfPages = contentHolder.childElementCount
    // eslint-disable-next-line no-undef
    console.log(this.$route.hash)
    // create the page scroller in the contentHolder.
    this.pages = new Pageable(contentHolder, {
      pips: false,
      orientation: 'vertical',
      // when scroll animation finish, update the current page number
      onFinish: ({ index }) => {
        this.activePage = index + 1
      }
    })
  }
}
</script>

<style lang="scss" scoped>
$grainer-color: #02f6b6;
$idle-color: #02f6b527;
#index {
  width: 100vw;
  height: 100vh;
  display: flex;
  flex-direction: row;
}

#index-nav {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
  text-align: center;
  width: 20%;
  max-width: 20%;
  align-content: center;
  line-height: 10vh;
}

#index-content {
  width: 80%;
}
</style>
