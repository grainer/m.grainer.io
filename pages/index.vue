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
        <start></start>
      </div>
      <div data-anchor="page2">
        <start></start>
      </div>
      <div data-anchor="page3">
        <start></start>
      </div>
      <div data-anchor="page4">
        <start></start>
      </div>
    </div>
  </div>
</template>

<script>
// eslint-disable-next-line no-unused-vars
import Pageable from 'pageable'
import Start from '@/components/Start'
import Pagination from '@/components/Pagination'
export default {
  components: {
    start: Start,
    pagination: Pagination
  },
  data() {
    return {
      pages: null,
      noOfPages: 0,
      activePage: 1
    }
  },
  mounted() {
    // get the element that holds the pages
    const contentHolder = document.getElementById('index-content')
    this.noOfPages = contentHolder.childElementCount

    // create the page scroller in the contentHolder.
    this.pages = new Pageable(contentHolder, {
      pips: false,
      orientation: 'vertical',
      onFinish: ({ index }) => {
        // when scroll animation finish, update the current page number
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
  top: 0%;
  width: 100vw;
  height: 100vh;
  display: inline-flex;
}

#index-nav {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
  text-align: center;
  width: 20%;
  z-index: 100;
  align-content: center;
  line-height: 10vh;
}

#index-content {
  width: 80%;
  z-index: 99;
}
</style>
