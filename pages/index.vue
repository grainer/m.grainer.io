<template>
  <div id="index">
    <div id="index-nav">
      <pagination :totalpages="noOfPages" :currentpage="activePage"></pagination>
    </div>
    <div id="index-content">
      <div data-anchor="page1">
        <start :showvideo="activePage === 1"></start>
      </div>
      <div data-anchor="page2">
        <crafting :showimage="activePage === 2"></crafting>
      </div>
      <div data-anchor="page3">
        <consultancy></consultancy>
      </div>
      <div data-anchor="page4">
        <development></development>
      </div>
      <div data-anchor="page5">
        <innovation></innovation>
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
import Consultancy from '@/components/Consultancy'
import Development from '@/components/Development'
import Innovation from '@/components/Innovation'
import Pagination from '@/components/Pagination'
import Next from '@/components/Next'
export default {
  components: {
    start: Start,
    pagination: Pagination,
    next: Next,
    crafting: Crafting,
    consultancy: Consultancy,
    development: Development,
    innovation: Innovation
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

    /*
      Pageable, a full page scrolling utility.
      original works by Karl (https://github.com/Mobius1/Pageable)
    */
    this.pages = new Pageable(contentHolder, {
      pips: false, // we need no pips
      orientation: 'vertical',
      onFinish: ({ index }) => {
        this.activePage = index + 1 // if scroll animation end, update active page no
      }
    })
  }
}
</script>

<style lang="scss" scoped>
@import '../assets/css/grainer';

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
  line-height: 10vh;
  max-width: 20%;
  align-content: center;
  -webkit-align-content: center;
}

#index-content {
  width: 80%;
}
</style>
