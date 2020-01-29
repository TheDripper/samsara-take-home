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
          <h2>{{ item.title }}</h2>
          <p>{{ item.copy }}</p>
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
        loop: true
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
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100vw;
    object-fit: cover;
    @screen md {
      height: 100%;
      width: 100%;
    }
  }
}
.swiper-pagination {
  position: absolute;
  bottom: 0;
  width: 100%;
  left: 0;
}
.swiper-slide {
  height: 490px;
}
img {
  position: absolute;
  object-fit: cover;
}
.carousel {
  transform: translate(-2rem);
  z-index: 2;
}
</style>
