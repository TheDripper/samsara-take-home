<template>
  <main id="browse">
    <Swiper :items="swiperItems" />
    <div class="bg-white accordion_container">
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
.accordion_container {
  max-width: 1400px;
  @apply relative w-full;
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
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
