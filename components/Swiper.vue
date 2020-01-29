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
          <div class="image-frame">
              <img 
                :id="`slider-${index}`" 
                :src="item.image"
              >
          </div>
          <div class="wrap">
            <h2 v-html="item.title" />
            <p v-html="item.copy"/>
          </div>
        </div>
      </div>
      <div class="swiper-nav flex py-8 lg:py-16">
        <img id="back" src="/left.svg" class="mr-4"/>
        <img id="next" src="/right.svg" />
      </div>
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
        loop: true,
        navigation: {
          prevEl: '#back',
          nextEl: '#next'
        },
        slidesPerView: 2,
        spaceBetween: 24,
        breakpoints: {
          768: {
            slidesPerView: 1
          }
        }
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
  @apply w-full px-6;
  max-width: 1200px;
}
h2 {
  font-size: 24px; 
  color: #00263E;
  @screen md {
    font-size: 34px;
  }
  @screen xl {
    font-size: 54px;
  }
}
.wrap {
  @apply p-8;
  height: 200px;
  @screen xl {
    height: 300px;
  }
}
#next,
#back {
  cursor: pointer;
  z-index: 2;
  width: 40%;
  max-width: 195px;
}
.image-frame {
  width: 100%;
  height: 55vw;
  overflow: hidden;
  @screen md {
    height: 28vw;
  }
  @screen xl {
    height: 350px;
  }
  img {
    object-fit: cover;
  }
}
</style>
