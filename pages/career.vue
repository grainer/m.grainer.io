<template>
  <div id="career" class="py-32 px-12 md:px-24">
    <row justify="center" addclass="py-24">
      <column justify="center" width="full">
        <textholder huge title="SKILLED, PROACTIVE & PASSIONATE? YOU’RE JUST THE RIGHT FIT!"></textholder>
      </column>
    </row>
    <row justify="center" addclass="py-24">
      <column justify="center" width="full">
        <textholder title="“DON’T JUST PRACTICE YOUR ART, BUT FORCE YOUR WAY INTO ITS SECRETS; FOR IT AND KNOWLEDGE CAN RAISE MAN TO THE DIVINE.”" author="BEETHOVEN">
          Your education and background are of no concern to us, as long as you have a passion for excellence and innovation, and a desire to channel it for the greater benefit of
          others.
        </textholder>
      </column>
    </row>
    <row justify="center" addclass="py-24">
      <column justify="center" width="full">
        <img :src="require('@/static/join-arrow.svg')" />
      </column>
      <!-- just an example if need to add later
        <column justify="center" width="full">
        <accordion bottomlined title="UI/UX DESIGNER" buttonlabel="APPLY NOW">
          Союз нерушимый республик свободных
          Сплотила навеки Великая Русь.
          Да здравствует созданный волей народов
          Единый, могучий Советский Союз!
          Славься, Отечество наше свободное,
          Дружбы, народов надежный оплот!
          Знамя советское, знамя народное
          Пусть от победы, к победе ведет!
        </accordion>
      </column>
      -->
    </row>
    <row justify="center" addclass="py-24">
      <column justify="center" width="full">
        <a href="mailto:info@grainer.io" style="font-family: Taviraj; font-size: 2.5rem; color: #02f6b6;">info@grainer.io</a>
      </column>
    </row>
  </div>
</template>

<script>
import Textholder from '@/components/Textholder.vue'
import Row from '@/components/Row.vue'
import Col from '@/components/Column.vue'
import Accordion from '@/components/Accordion.vue'

export default {
  components: {
    column: Col,
    row: Row,
    textholder: Textholder,
    // eslint-disable-next-line vue/no-unused-components
    accordion: Accordion
  }
}
</script>
