<template functional>
  <div class="card-container">
    <img :src="props.img" class="avatar" />
    <dl>
      <dt>{{ props.name }}</dt>
      <dd>{{ props.position }}</dd>
    </dl>
    <ul>
      <li v-if="props.social.facebook">
        <a :href="props.social.facebook" class="interactive" target="_blank">
          <i class="fab fa-facebook-f"></i>
        </a>
      </li>
      <li v-if="props.social.instagram">
        <a :href="props.social.instagram" class="interactive" target="_blank">
          <i class="fab fa-instagram"></i>
        </a>
      </li>
      <li v-if="props.social.linkedin">
        <a :href="props.social.linkedin" class="interactive" target="_blank">
          <i class="fab fa-linkedin"></i>
        </a>
      </li>
      <li v-if="props.social.medium">
        <a :href="props.social.medium" class="interactive" target="_blank">
          <i class="fab fa-medium-m"></i>
        </a>
      </li>
      <li v-if="props.social.behance">
        <a :href="props.social.behance" class="interactive" target="_blank">
          <i class="fab fa-behance"></i>
        </a>
      </li>
    </ul>
  </div>
</template>

<script>
import avtrMajed from '@/assets/img/Majed.svg'

export default {
  name: 'Namecard',
  functional: true,
  props: {
    img: {
      type: String,
      default: avtrMajed
    },
    name: {
      type: String,
      default: 'This is the name'
    },
    position: {
      type: String,
      default: 'this is position'
    },
    social: {
      type: Object,
      default: () => ({
        facebook: undefined,
        instagram: undefined,
        linkedin: undefined,
        medium: undefined,
        behance: undefined
      })
    }
  }
}
</script>

<style lang="scss" scoped>
@import url('https://fonts.googleapis.com/css?family=Taviraj:400,700&display=swap');

%flexbox {
  display: flex;
  justify-content: center;
}

.card-container {
  @extend %flexbox;
  flex-direction: column;
  width: 20rem;
  height: 20rem;
  margin: 1rem 0 1rem 0;

  img {
    height: 8rem;
  }

  dl {
    margin: 2rem 0 0.5rem 0;
    font-family: Taviraj;
    text-align: center;

    dt {
      font-size: 0.8rem;
      font-weight: 700;
      color: #02f6b6;
      text-transform: uppercase;
    }

    dd {
      font-size: 0.7rem;
      font-weight: 400;
      color: #ffffff;
    }
  }

  ul {
    @extend %flexbox;
    flex-direction: row;
    font-size: 0.8rem;
    color: #02f6b6;

    li {
      margin: 0 0.5rem 0 0.5rem;
      padding: 0.3rem 0.5rem 0.3rem 0.5rem;
      border: 1px solid #02f6b6;
      border-radius: 7px 0px 7px 7px;
    }
  }

  &:hover {
    background-color: #02f6b6;

    dt,
    dd,
    li {
      color: black !important;
    }

    li {
      border: 2px solid black;
    }
  }
}
</style>
