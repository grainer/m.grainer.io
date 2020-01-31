<template>
  <div class="w-full h-full flex flex-col justify-center items-center">
    <div class="w-2/3 flex flex-row items-center mt-20">
      <div class="w-3 h-10 sm:h-24 bg-gr-green-light"></div>
      <h1 class="font-h craft-line sm:text-4xl ml-3 w-1/2">How Can We Help You?</h1>
    </div>
    <div class="w-full h-full flex justify-center items-center">
      <div class="swiper-inner h-full w-full mt-5 flex justify-center items-start flex-col relative overflow-hidden">
        <swiper :options="swiperOption" class="w-full flex justify-center items-center" @slideChange="setStyle">
          <div slot="pagination" class="swiper-pagination absolute top-0 ml-5 w-2/3"></div>
          <swiper-slide>
            <div class="p-10">
              <h1 class="font-h craft-line text-4xl">Consulting</h1>
              <div class="w-16 h-3 bg-gr-green-light mt-2"></div>
              <p class="mt-4">
                We offer consulting and technology implementation services to businesses that want to re-define their customer success stories through digital transformation.
              </p>

              <button type="submit" class="px-6 py-2 rounded-lg rounded-tr-none border-gr-green-light border-2 mt-5 font-sh outline-none slide interactive" @click="goToContact">
                Talk To Us
              </button>
            </div>
          </swiper-slide>
          <swiper-slide>
            <div class="p-10">
              <h1 class="font-h craft-line">Development</h1>
              <div class="w-16 h-3 bg-gr-green-light mt-2"></div>
              <p class="mt-4">
                Our dedicated team of technology experts partner with you and usher you through every step of the way to translate your ideas into robust solutions.
              </p>

              <button type="submit" class="px-6 py-2 rounded-lg rounded-tr-none border-gr-green-light border-2 mt-5 font-sh outline-none slide interactive" @click="goToContact">
                Get In Touch
              </button>
            </div>
          </swiper-slide>
          <swiper-slide>
            <div class="p-10">
              <h1 class="font-h craft-line">Innovation Hub</h1>
              <div class="w-16 h-3 bg-gr-green-light mt-2"></div>
              <p class="mt-4">
                We constantly research and develop solutions for the right use case and corresponding market. We are passionate about emerging technologies in the areas of
                blockchain, artificial intelligence (AI), machine learning, cybersicurity, data sceince, and the Internet of Things.
              </p>
              <button type="submit" class="px-6 py-2 rounded-lg rounded-tr-none border-gr-green-light border-2 mt-5 font-sh outline-none slide interactive" @click="goToContact">
                Reach Out
              </button>
            </div>
          </swiper-slide>
        </swiper>
      </div>
    </div>
  </div>
</template>

<script>
// require styles
import 'swiper/dist/css/swiper.css'

import { swiper, swiperSlide } from 'vue-awesome-swiper'

export default {
  components: {
    swiper,
    swiperSlide
  },
  data() {
    return {
      swiperOption: {
        effect: 'cube',
        grabCursor: true,
        cubeEffect: {
          shadow: true,
          slideShadows: true,
          shadowOffset: 50,
          shadowScale: 1
        },
        mousewheel: true,
        pagination: {
          el: '.swiper-pagination'
        }
      }
    }
  },
  mounted() {
    this.setStyle()
  },
  methods: {
    setStyle() {
      const paginations = document.getElementsByClassName('swiper-pagination-bullet')

      for (let i = 0; i < paginations.length; i++) {
        const bullet = paginations[i]
        bullet.style = `width: 3em !important;
                      height: 0.5em !important;
                      margin: 0 0 !important;
                      border-radius: 0 !important;`
      }
      const highlitedPagination = document.getElementsByClassName('swiper-pagination-bullet-active')
      highlitedPagination[0].style = `width: 3em !important;
                                    height: 0.5em !important;
                                    margin: 0 0 !important;
                                    border-radius: 0 !important;
                                    opacity: 1;
                                    background: #02f6b6 !important;`

      const shadow = document.getElementsByClassName('swiper-cube-shadow')
      shadow[0].style = 'pointer-events: none !important;'
    },
    goToContact() {
      this.$store.commit('goto', '#contact')
    }
  }
}
</script>

<style scoped>
/* .swiper-inner {
  width: 700px;
  height: 520px;
}
.swiper-slide {
  width: 100%;
  background-color: rgb(0, 66, 46, 0.53);
}
.swiper-container {
  width: 650px !important;
  height: 500px !important;
  width: 100% !important;
  height: 500px !important;
  position: absolute;
  margin-left: 0;
}
.swiper-slide {
  background-position: center;
  background-size: cover;
} */

.swiper-box {
  width: 100%;
  height: 100%;
  margin: 0 auto;
}
.swiper-item {
  height: 100%;
  text-align: center;
  font-size: 18px;
  background: #fff;
  /* Center slide text vertically */
  display: -webkit-box;
  display: -ms-flexbox;
  display: -webkit-flex;
  display: flex;
  -webkit-box-pack: center;
  -ms-flex-pack: center;
  -webkit-justify-content: center;
  justify-content: center;
  -webkit-box-align: center;
  -ms-flex-align: center;
  -webkit-align-items: center;
  align-items: center;
}
.swiper-pagination-bullet-active {
  opacity: 1;
  background: #02f6b6 !important;
}
</style>
