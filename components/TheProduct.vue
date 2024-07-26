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
    }
    &__slider {
      padding: 60px;
      background-color: var(--grey);
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
        grid-template-columns: 1fr 1fr;
        align-items: center;
        gap: 30px;
      }
      &__title {
        font-size: 26px;
        font-weight: 700;
        margin-bottom: 20px;
      }
      &__text {
        font-size: 16px;
        font-weight: 400;
      }
    }
    .swiper-button-prev, .swiper-button-next {
      left: auto;
      top: auto;
      right: 0;
      bottom: 20px;
    }
    .swiper-button-prev {
      right: 100px;
    }
  }
</style>