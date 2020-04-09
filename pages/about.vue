<template>
  <div class="my-24">
    <!-- about grainer -->
    <row justify="center md:justify-between" wrap="reverse" align="center" addclass="px-12 md:px-24">
      <column justify="center md:justify-start my-12" width="full">
        <h1 class="boom">
          ABOUT
          <br />
          <span class="px-4">GRAINER</span>
        </h1>
      </column>
      <column width="full" justify="center">
        <img id="logo-grainer" :src="require('@/static/logo-outline.svg')" i />
      </column>
    </row>

    <!-- our passion -->
    <row justify="between" wrap="reverse" align="center" addclass="my-24 px-12 md:px-24">
      <column width="full md:w-1/2">
        <textholder title="Our passion is to transform processes and enhance experiences for businesses that want to win"></textholder>
      </column>
      <column width="full md:2/5">
        <img :src="require('@/assets/img/passion.png')" height="100%" />
      </column>
    </row>

    <!-- mission und visyon -->
    <row justify="between" addclass="my-24 px-12 sm:px-24">
      <column width="full md:w-4/12">
        <textholder title="MISSION">
          ● To exceed the expectations of our clients by guiding & developing great solutions
          <br />
          <br />● To invent, nurture, and acquire brilliant technologies
        </textholder>
      </column>
      <column width="full md:w-7/12 my-12 md:py-0">
        <textholder title="VISION">
          To be at the forefront of tech innovation
          <br />
          <!-- <br />Over time, we have been successful in bringing together like-minded businesses and technology developers with the deepest knowledge in their own domains. We believe
          that technology is an asset through which we challenge the norms and disrupt the status quo! -->
        </textholder>
      </column>
    </row>

    <!-- memberships & accreditation -->
    <row justify="between" align="center" addclass="my-24 px-12 sm:px-24">
      <column width="full md:w-4/12">
        <textholder title="MEMBERSHIPS"></textholder>
      </column>
      <column justify="around flex-wrap" align="center" width="full md:w-3/12">
        <a href="https://www.fintechmalaysia.org/" target="_blank">
          <img :src="require('@/assets/img/faom.png')" width="180px" />
        </a>
      </column>
      <column justify="around flex-wrap" align="center" width="full md:w-3/12">
        <a href="https://access-my.org/" target="_blank">
          <img :src="require('@/assets/img/access.png')" width="362px" />
        </a>
      </column>
    </row>

    <!-- team avatar -->
    <row justify="left" addclass="px-12">
      <column width="full">
        <textholder title="THE TEAM"></textholder>
      </column>
    </row>
    <row justify="center">
      <column v-for="person in teams" :key="person.name" justify="center" width="1/2">
        <namecard :img="person.img" :name="person.name" :position="person.position" :social="person.social"></namecard>
      </column>
    </row>
    <row justify="left" addclass="px-12">
      <column width="full">
        <joincard></joincard>
      </column>
      <contact title="We would like to hear from you"></contact>
    </row>
  </div>
</template>

<script>
import Vue from 'vue'
import Textholder from '@/components/Textholder.vue'
import Namecard from '@/components/Namecard.vue'
import Joincard from '@/components/Joincard.vue'
import Row from '@/components/Row.vue'
import Col from '@/components/Column.vue'
import Contact from '@/components/Contact.vue'

import avAmine from '@/assets/img/Amine.svg'
// import avAnas from '@/assets/img/Anas.svg'
import avDanial from '@/assets/img/Danial.svg'
import avFaraz from '@/assets/img/Faraz.svg'
import avImam from '@/assets/img/Imam.svg'
import avIskandar from '@/assets/img/Iskandar.svg'
import avMajed from '@/assets/img/Majed.svg'
// import avNur from '@/assets/img/Nur.svg'

export default Vue.extend({
  components: {
    column: Col,
    row: Row,
    textholder: Textholder,
    namecard: Namecard,
    joincard: Joincard,
    contact: Contact
  },
  data() {
    return {
      teams: [
        {
          img: avMajed,
          name: 'ABDUL MAJED AHMAD',
          position: 'Co-Founder & CEO',
          social: { linkedin: 'https://www.linkedin.com/in/amajed/' }
        },
        {
          img: avAmine,
          name: 'BEKKAI AMINE FATAH',
          position: 'Co-Founder & CTO',
          social: { linkedin: 'https://www.linkedin.com/in/amine-fatah-61312a121/' }
        },
        {
          img: avDanial,
          name: 'danial syahiran ho',
          position: 'Business Development Lead',
          social: { linkedin: '' }
        },
        // {
        //   img: avNur,
        //   name: 'NUR AZEHA YUSOF',
        //   position: 'Front-End Developer',
        //   social: { linkedin: 'https://www.linkedin.com/in/zeha-yusof-9307b8146' }
        // },
        {
          img: avIskandar,
          name: 'MUHAMAD ISKANDAR',
          position: 'Back-End Developer',
          social: { linkedin: 'http://www.linkedin.com/in/mehmedskndr' }
        },
        {
          img: avImam,
          name: 'Imam Khaira',
          position: 'Front-End Developer',
          social: { linkedin: 'https://www.linkedin.com/in/imam-k-89735b112' }
        },
        // {
        //   img: avAnas,
        //   name: 'MOHAMMAD ANAS',
        //   position: 'Web Developer',
        //   social: { linkedin: 'https://www.linkedin.com/in/muhamad-anas/' }
        // },
        {
          img: avFaraz,
          name: 'MUHAMMED FARAZ',
          position: 'Brand Strategist',
          social: { linkedin: 'https://www.linkedin.com/in/muhammed-faraz-faizal-6345b1155/' }
        }
      ],
      social: [
        {
          type: 'facebook-f',
          href: 'https://www.facebook.com'
        },
        {
          type: 'twitter',
          href: 'https://www.twitter.com'
        },
        {
          type: 'instagram',
          href: 'https://www.instageram.com'
        },
        {
          type: 'youtube',
          href: 'https://www.youtube.com'
        },
        {
          type: 'linkedin',
          href: 'https://www.linkedin.com'
        }
      ]
    }
  }
})
</script>

<style lang="scss" scoped>
@import '../assets/css/grainer';

/* font size is set by taiwind. */
.boom {
  font-family: Roboto;
  font-weight: bold;
  line-height: 1.2;
  color: white;

  font-size: 3rem;
  text-align: center;

  span {
    color: $bg-color;
    background-color: $grainer-color;
  }
}

#logo-grainer {
  width: 80vw;
  max-height: 80vh;
}
</style>
