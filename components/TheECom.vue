<template>
  <div class="ecom">
    <div class="container">
      <div class="ecom__inner r-40">
        <div class="ecom__info">
          <div class="ecom__title title">Продукты для<span class="text-gradient">eCom</span></div>
          <div class="ecom__subtitle">Используйте готовые продукты от нашей компании или закажите персональную разработку.</div>
        </div>
        <div class="ecom-card">
          <div class="ecom-card__list">
            <NuxtLink
              v-for="(item, i) in card"
              :key="i" 
              :to="item.url"
              class="ecom-card__item r-40">
              <div class="ecom-card__img">
                <img :src="item.ico" alt="svg">
              </div>
              <div class="ecom-card__description">
                <div class="ecom-card__title">{{ item.title }}</div>
                <div class="ecom-card__text">{{ item.text }}</div>
              </div>
            </NuxtLink>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      card: [],
    }
  },
  async mounted() {
    const cards = []
    cards.push(
      {
        ico: (await import("@/assets/img/svg/item39.svg")).default,
        title: 'Продажи на маркетплейсах',
        text: 'Автоматизация продаж на универсальных маркетплейсах',
        url: '#'
      },
      {
        ico: (await import("@/assets/img/svg/item38.svg")).default,
        title: 'Интернет-магазин',
        text: 'Автоматизация онлайн-продаж для вашего интернет-магазина',
        url: '#'
      },
      {
        ico: (await import("@/assets/img/svg/item9.svg")).default,
        title: 'Нишевые маркетплейсы',
        text: 'Управление собственным маркетплейсом',
        url: '#'
      },
      {
        ico: (await import("@/assets/img/svg/item7.svg")).default,
        title: 'Шина данных (ESB)',
        text: 'Управление обменом данных и интеграции',
        url: '#'
      },
    )
    this.card = cards
	}
}
</script>

<style lang="scss">
  .ecom {
    &__inner {
      background-color: var(--grey);
      padding: 80px;
      display: grid;
      grid-template-columns: 0.56fr 1fr;
      gap: 70px;
      @media(max-width: 1300px) {
        gap: 30px;
        grid-template-columns: 1fr;
      }
      @media(max-width: 1023px) {
        padding: 40px 15px;
      }
    }
    &__info {}
    &__title {
      margin-bottom: 20px;
      @media(max-width: 1023px) {
        text-align: center;
        display: flex;
        align-items: center;
        justify-content: center;
        span {
          margin-left: 0.3em;
        }
      }
    }
    &__subtitle {
      font-size: 30px;
      font-weight: 400;
      color: var(--text);
      @media(max-width: 1023px) {
        font-size: 16px;
        text-align: center;
      }
    }
  }
  .ecom-card {
    &__list {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 20px;
      @media(max-width: 767px) {
        grid-template-columns: 1fr;
      }
    }
    &__item {
      box-shadow: var(--shadow);
      padding: 30px;
      transition: 0.3s;
      &:hover {
        @media(min-width: 1023px) {
          box-shadow: inset 2px 2px 12px 0px rgba(136, 165, 191, 0.6),inset -2px -3px 6px 0px rgba(136, 165, 191, 0.3),inset -3px -4px 6px 0px rgb(255, 255, 255);
        }
      }
      @media(max-width: 1023px) {
        padding: 20px;
        height: 100%;
      }
    }
    &__img {
      width: 100px;
      height: 100px;
      margin: 0 auto 60px;
      @media(max-width: 1023px) {
        margin-bottom: 20px;
      }
      @media(max-width: 767px) {
        width: 65px;
        height: 65px;
      }
      img {
        width: 100%;
        height: 100%;
        object-fit: cover;
      }
    }
    &__description {
      text-align: center;
    }
    &__title {
      font-size: 26px;
      font-weight: 700;
      color: var(--text);
      margin-bottom: 20px;
      @media(max-width: 767px) {
        font-size: 18px;
      }
    }
    &__text {
      font-size: 18px;
      font-weight: 400;
      color: var(--text);
      @media(max-width: 767px) {
        font-size: 14px;
      }
    }
  }
</style>