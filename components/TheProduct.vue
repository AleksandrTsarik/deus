<template>
  <div class="product">
    <div class="container">
      <div class="product__inner">
        <div class="product__title title"><span class="text-gradient">Название продукта</span> для&nbsp;средних и&nbsp;крупных торговых и&nbsp;производственных компаний</div>
        <div class="product__slider r-40">
          <UITheSwiper
            :slider="slider"
            :options="optionsSlider" 
            class="slider-product slider-navigation"
          />
        </div>
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
        pagination: true,
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
        img: (await import("@/assets/img/product/item1.png")).default,
        title: 'Динамическое ценообразование',
        text: 'Корректировка цены товара в диапазоне 5% приводит к росту количества заказов на 28% в течение 24 часов',
      },   
      {
        img: (await import("@/assets/img/product/item2.png")).default,
        title: 'Новая бизнес модель',
        text: 'Возможность получения комиссии с транзакций между продавцами и покупателями на платформе.',
      },  
      {
        img: (await import("@/assets/img/product/item3.png")).default,
        title: 'Продажи',
        text: 'Увеличение конверсии в продажу',
      },  
    )
    this.slider = sliders
	}
}
</script>

<style lang="scss">
  .product {
    &__inner {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 100px;
      @media(max-width: 1500px) {
        gap: 40px;
      }
      @media(max-width: 1400px) {
        grid-template-columns: 1fr;
      }
    }
    &__slider {
      padding: 60px;
      background-color: var(--grey);
      @media(max-width: 1500px) {
        padding: 30px;
      }
    }
  }
  .slider-product {
    .swiper-slide {
      background-color: var(--grey);
    }
    .slider {
      &__wrap {
        padding-bottom: 70px;
      }
      &__block {
        display: grid;
        grid-template-columns: 280px 1fr;
        align-items: center;
        gap: 30px;
        @media(max-width: 767px) {
          grid-template-columns: 1fr;
        }
      }
      &__title {
        font-size: 26px;
        font-weight: 700;
        margin-bottom: 20px;
        @media(max-width: 767px) {
          text-align: center;
          font-size: 16px;
          margin-bottom: 10px;
        }
      }
      &__text {
        font-size: 16px;
        font-weight: 400;
        @media(max-width: 767px) {
          text-align: center;
          font-size: 14px;
        }
      }
      &__img {
        height: 280px;
        @media(max-width: 767px) {
          width: 220px;
          height: 220px;
          margin: 0 auto;
        }
        img {
          width: 100%;
          height: 100%;
          object-fit: cover;
        }
      }
    }
    .swiper-button-prev, .swiper-button-next {
      left: auto;
      top: auto;
      right: 20px;
      bottom: 20px;
      @media(max-width: 767px) {
        display: none;
      }
    }
    .swiper-button-prev {
      right: 105px;
    }
    .swiper-pagination-bullet {
      width: 14px;
      height: 14px;
      background-color: #fff;
      opacity: 1;
      overflow: hidden;
      
    }
    .swiper-pagination-bullet-active {
      position: relative;
      &:after {
        content: '';
        background-image: url('@/assets/img/bullet.svg');
        background-position: 50% 50%;
        background-repeat: no-repeat;
        width: 1em;
        height: 1em;
        display: block;
        position: absolute;
        top: -2px;
        right: -4px;
      }
    }
    .swiper-pagination {
      text-align: left;
      padding-left: 40px;
      @media(max-width: 767px) {
        margin: 0 auto;
        text-align: center;
        padding: 0;
      }
    }
  }
</style>