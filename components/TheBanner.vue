<template>
  <div class="container">
    <div class="banner r-40">
      <div class="banner__slider">
        <UITheSwiper
          :slider="slider"
          :options="optionsSlider" 
          class="slider-banner slider-navigation"
        />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      slider: [],
      optionsSlider: {
        loop: false,
        slidesPerView: 1,
        slidesPerGroup: 1,
        centeredSlides: false,
        spaceBetween: 35,
        pagination: false,
        navigation: true,
        modules: "modules",
        mousewheel: false,
        navigation: true,
        effect: 'fade'
      }
    }
  },
  async mounted() {
    const sliders = []
    sliders.push(
      {
        img: (await import("@/assets/img/top-man.webp")).default,
        title: 'Заголовок для слайдера',
        text: 'Краткое описание УТП продукта, максимально две строки текста1',
        btn: 'Смотреть решение',
      },
      {
        img: (await import("@/assets/img/top-man.webp")).default,
        title: 'Заголовок для слайдера',
        text: 'Краткое описание УТП продукта, максимально две строки текста2',
        btn: 'Смотреть решение',
      },
      {
        img: (await import("@/assets/img/top-man.webp")).default,
        title: 'Заголовок для слайдера',
        text: 'Краткое описание УТП продукта, максимально две строки текста3',
        btn: 'Смотреть решение',
      },
      {
        img: (await import("@/assets/img/top-man.webp")).default,
        title: 'Заголовок для слайдера',
        text: 'Краткое описание УТП продукта, максимально две строки текста4',
        btn: 'Смотреть решение',
      },
    )
    this.slider = sliders
	}
}
</script>

<style lang="scss">
  .banner {
    background-color: var(--grey);
  }
  .slider-banner {
    .swiper {
      z-index: 0;
    }
    .swiper-slide {
      background-color: var(--grey);
      z-index: 0;
    }
    .slider {
      &__wrap {
        padding: 80px 80px 0;
        @media(max-width: 1240px) {
          padding: 40px 40px;
        }
        @media(max-width: 767px) {
          padding: 40px 20px 0;
        }
      }
      &__block {
        display: flex;
        flex-direction: row-reverse;
        height: 100%;
        @media(max-width: 1023px) {
          flex-wrap: wrap;
        }
      }
      &__img {
        position: relative;
        flex: 0 0 45%;
        max-width: 45%;
        @media(max-width: 1023px) {
          flex: 0 0 100%;
          max-width: 100%;
          order: 2;
          margin: 0 auto;
          text-align: center;
          padding-bottom: 600px;
        }
        @media(max-width: 767px) {
          padding-bottom: 98%;
        }
        @media(max-width: 575px) {
          padding-bottom: 0;
          padding-top: 83px;
        }
        img {
          position: absolute;
          left: 0;
          bottom: 0;
          width: 100%;
          height: 100%;
          @media(max-width: 1240px) {
            bottom: -40px;
            width: auto;
            height: auto;
          }
          @media(max-width: 767px) {
            bottom: 0;
          }
          @media(max-width: 575px) {
            height: 270px;
            margin: 0 auto;
            display: block;
            position: relative;
            bottom: auto;
            left: auto;
          }
        }
      }
      &__description {
        display: flex;
        flex-direction: column;
        flex: 0 0 55%;
        max-width: 55%;
        @media(max-width: 1023px) {
          flex: 0 0 100%;
          max-width: 100%;
          order: 1;
        }
      }
      &__title {
        padding-top: 50px;
        background: linear-gradient(137.70deg, rgb(57, 199, 236),rgb(57, 199, 236),rgb(0, 80, 236));
        -webkit-background-clip: text;
        -webkit-text-fill-color: transparent;
        color: #0B2349;
        display: table;
        font-size: 50px;
        font-weight: 700;
        line-height: 120%;
        margin-bottom: 20px;
        @media(max-width: 1500px) {
          padding-top: 0;
        }
        @media(max-width: 1240px) {
          font-size: 40px;
        }
        @media(max-width: 1023px) {
          text-align: center;
        }
        @media(max-width: 767px) {
          font-size: 30px;
          margin-bottom: 15px;
        }
      }
      &__text {
        color: var(--text);
        font-size: 30px;
        font-weight: 400;
        line-height: 140%;
        margin-bottom: 50px;
        @media(max-width: 1240px) {
          font-size: 24px;
        }
        @media(max-width: 1023px) {
          text-align: center;
        }
        @media(max-width: 767px) {
          font-size: 14px;
          margin-bottom: 20px;
        }
      }
      &__btn {
        margin-bottom: 180px;
        @media(max-width: 1400px) {
          margin-bottom: 140px;
        }
        @media(max-width: 1023px) {
          margin: 0 auto;
        }
      }
    }
    .swiper-button-prev, .swiper-button-next {
      top: auto;
      bottom: 40px;
      right: auto;
      left: 80px;
      @media(max-width: 1240px) {
        left: 40px;
      }
      @media(max-width: 1023px) {
        bottom: 550px;
        left: 45%;
        transform: translateX(-50%);
      }
      @media(max-width: 767px) {
        bottom: 63%;
        transform: translate(-50%, 50%);
      }
      @media(max-width: 575px) {
        bottom: 280px;
        transform: translateX(-50%);
        left: 35%;
      }
    }
    .swiper-button-next {
      left: 165px;
      @media(max-width: 1240px) {
        left: 125px;
      }
      @media(max-width: 1023px) {
        left: 55%;
      }
      @media(max-width: 575px) {
        left: 65%;
      }
    }
  }
</style>