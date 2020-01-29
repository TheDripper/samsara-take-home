<template>
  <main id="browse">
    <h1 class="text-white">Browse the Libraries Below</h1>
    <Swiper :items="swiperItems" />
    <img id="burst" src="/burst.png" />
    <div class="bg-white accordion_container">
      <h2>The importance of brand consistency</h2>
      <Accordion v-for="(item, i) in accordionItems" :content="item.content" />
    </div>
  </main>
</template>

<script>
import Logo from '~/components/Logo.vue'
import Accordion from '~/components/Accordion.vue'
import Swiper from '~/components/Swiper.vue'

export default {
  data() {
    return {
      accordionItems: [
        {
          content: {
            listItem: 'Brand Design',
            accordionText: 'As we continue to scale globally, keeping our brand materials consistent across channels becomes increasingly important. We want to ensure a consistent standard of excellence in how we present ourselves to our current and future customers.'
          }
        },
        {
          content: {
            listItem: 'Typography',
            accordionText: 'As we continue to scale globally, keeping our brand materials consistent across channels becomes increasingly important. We want to ensure a consistent standard of excellence in how we present ourselves to our current and future customers.'
          }
        },
        {
          content: {
            listItem: 'Colors',
            accordionText: 'As we continue to scale globally, keeping our brand materials consistent across channels becomes increasingly important. We want to ensure a consistent standard of excellence in how we present ourselves to our current and future customers.'
          }
        }
      ],
      swiperItems: [
        {
          image: '/one.png',
          title: 'Photography-<br /> Office',
          copy: 'Internal and Customer Events',
          id: 'one'
        },
        {
          image: '/two.png',
          title: 'Illustrations',
          copy: 'Illustrated Assets and Icons',
          id: 'two'
        },
        {
          image: '/three.png',
          title: 'Photography - Events',
          copy: 'Office and Employees',
          id: 'three'
        },
        {
          image: '/four.png',
          title: 'Photography - Products',
          copy: 'In Situ and Renderings',
          id: 'four'
        }
      ]

    }
  },
  components: {
    Accordion,
    Swiper,
    Logo
  }
}
</script>

<style lang="scss" scoped>
main {
  max-width: 100%;
  overflow-y: hidden;
}
#browse {
  @apply flex flex-col items-center;
  min-height: calc(100vh - 110px);
}
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #00263E;
  letter-spacing: 1px;
}

.links {
  padding-top: 15px;
}
#burst {
  margin-left: auto;
  @screen md {
    transform: translate(-5%, -34%);
  }
}
h1 {
  @apply text-3xl p-6 w-full;
  max-width: 1200px;
  @screen md {
    @apply text-5xl text-left px-6;
  }
  @screen lg {
    @apply text-6xl py-16;
  }
}
h2 {
  font-size: 24px; 
  @screen md {
    font-size: 34px;
  }
  @screen xl {
    font-size: 54px;
  }
}
.accordion_container {
  max-width: 1400px;
  @apply relative w-full pb-64;
  &:before {
    background: white;
    content: '';
    position: absolute;
    top: 0px;
    left: 0px;
    transform: rotate(-20deg) translateY(-15%);
    width: 200vw;
    height: 200vw;
  }
  h2 {
    color: #00263E;
  }
}
</style>
