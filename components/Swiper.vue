<template>
  <div class="carousel">
    <div
      v-swiper:swiper="swiperOptions"
    >
      <div class="swiper-wrapper">
        <div
          v-for="(item, index) in items"
          :key="item.id"
          class="swiper-slide"
        >
            <img 
              :id="`slider-${index}`" 
              :src="item.image"
            >
          <div class="wrap">
            <h2 v-html="item.title" />
            <p v-html="item.copy"/>
          </div>
        </div>
      </div>
      <div class="swiper-pagination swiper-pagination-bullets flex items-center justify-center py-8" />
    </div>
  </div>
</template>

<script>
export default {
  props: {
    items: {
      type: Array,
      default: () => []
    }
  },
  data() {
    return {
      swiperOptions: {
        pagination: {
          el: '.swiper-pagination',
          clickable: true
        },
        slidesPerView: 2,
        loop: true,
        spaceBetween: 50
      }
    }
  },
}
</script>
<style scoped lang="scss">
/deep/ {
  .swiper-pagination-bullet {
    border-radius: initial;
    width: 35px;
    height: 4px;
    margin-left: 2px;
    margin-right: 2px;
    opacity: 0.15;
  }
  .swiper-pagination-bullet-active {
    background: black;
    opacity: 1;
  }
}
.swiper-wrapper {
  width: calc(100vw + 4rem);
  img {
    width: 100%;
  }
}
.swiper-pagination {
  position: absolute;
  bottom: 0;
  width: 100%;
  left: 0;
}
.swiper-slide {
  background: white;
}
.carousel {
  z-index: 2;
  width: 1200px;
  margin-bottom: 600px;
}
h2 {
  font-size: 24px; 
  @screen md {
    font-size: 54px;
  }
}
.wrap {
  @apply p-8 pt-12;
  @screen md {
    height: 400px;
  }
}
</style>
