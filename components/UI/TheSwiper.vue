<template>
  <Swiper
    class="slider"
    :modules="modules"
    :loop="options.loop"
    :navigation="options.navigation"
    :slidesPerView="options.slidesPerView"
    :slidesPerGroup="options.slidesPerGroup"
    :centeredSlides="options.centeredSlides"
    :spaceBetween="options.spaceBetween"
    :pagination="options.pagination"
    :breakpoints="options.breakpoints"
    :effect="options.effect"
    :mousewheel="options.mousewheel"
  >
    <SwiperSlide
      v-for="(slide, i) in slider"
      :key="i"
    >
      <div class="slider__wrap">
        <div class="slider__block">
          <div v-if="slide.img" class="slider__img">
            <img :src="slide.img" alt="...">
          </div>
          <div class="slider__description">
            <h3 v-if="slide.title" class="slider__title">{{ slide.title }}</h3>
            <div v-if="slide.text" class="slider__text">{{ slide.text }}</div>
            <div v-if="slide.btn" class="slider__btn"><UITheButton :label="slide.btn" class="btn btn-dark" /></div>
          </div>
        </div>
      </div>
    </SwiperSlide>
    <SwiperControls />
  </Swiper>
</template>

<script>
import { Swiper, SwiperSlide } from 'swiper/vue';

import 'swiper/css';

import 'swiper/css/effect-coverflow';
import 'swiper/css/effect-fade';
import 'swiper/css/pagination';
import 'swiper/css/navigation';

import { Pagination, Navigation, Mousewheel, EffectCoverflow, EffectFade } from 'swiper/modules';
export default {
  components: {
    Swiper,
    SwiperSlide,
  },
  props: {
    slider: {type: Array, default: [], require: false},
    options: {type: Object, default: {}, require: false}
  },
  mounted() {
    console.log(this.options)
  },
  setup() {
      return {
        modules: [ Pagination, Navigation, Mousewheel, EffectCoverflow, EffectFade]
      };
    },
}
</script>

<style lang="scss">
.slider-navigation {
  .swiper-button-prev, .swiper-button-next {
    width: 56px;
    height: 56px;
    background: rgb(239, 241, 247);
    border-radius: 8px;
    box-shadow: 5px 5px 20px 0px rgba(200, 212, 223, 0.8),3px 3px 10px 0px rgba(210, 218, 227, 0.5),-3px -3px 10px 0px rgb(255, 255, 255),-5px -5px 18px 0px rgba(255, 255, 255, 0.9);
    transition: 0.3s;
    &:hover {
      @media(min-width: 1023px) {
        box-shadow: inset 2px 2px 12px 0px rgba(136, 165, 191, 0.6),inset -2px -3px 6px 0px rgba(136, 165, 191, 0.3),inset -3px -4px 6px 0px rgb(255, 255, 255);
      }
    }

    &::after {
      content: '';
      display: block;
      background-image: url('@/assets/img/arrow.svg');
      background-size: cover;
      background-position: 50% 50%;
      background-repeat: no-repeat;
      width: 15px;
      height: 11px;
    }
  }
  .swiper-button-next {
    &::after {
      transform: rotate(180deg);
    }
  }
}
</style>