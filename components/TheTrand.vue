<template>
  <div class="trand">
    <div class="container">
      <div class="trand__inner">
        <div class="trand__list">
          <div
            v-for="(item, i) in card"
            :key="i" 
            class="trand__item trand-card r-40">
              <div class="trand-card__ico">
                <img :src="item.ico" alt="svg">
              </div>
              <div class="trand-card__description">{{ item.description }}</div>
            </div>
        </div>
        <TheBlueBlock :title="'Новые  тренды и&nbsp;инструменты для&nbsp;развития бизнеса'" :row="'Персональная эксперт-сессия'" />
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
        ico: (await import("@/assets/img/svg/item9.svg")).default,
        description: 'Разработка и автоматизация интернет-магазинов, маркетплейсов',
      },
      {
        ico: (await import("@/assets/img/svg/item4.svg")).default,
        description: 'Проекты любой сложности и конфигурации с помощью модульной архитектуры',
      },
      {
        ico: (await import("@/assets/img/svg/item5.svg")).default,
        description: 'ИТ-экспертиза и бизнес-консалтинг для достижения поставленных целей',
      },
      {
        ico: (await import("@/assets/img/svg/item7.svg")).default,
        description: 'Используем две модели развертывания SaaS',
      },
    )
    this.card = cards
	}
}
</script>

<style lang="scss">
  .trand {
    &__inner {} 
    &__list {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      gap: 20px;
      margin-bottom: 150px;
      @media(max-width: 1240px) {
        grid-template-columns: 1fr 1fr;
      }
      @media(max-width: 767px) {
        grid-template-columns: 1fr;
        margin-bottom: 60px;
      }
    } 
    &__item {
      background-color: var(--grey);
      padding: 30px;
    } 
  }
  .trand-card {
    display: flex;
    flex-direction: column;
    min-height: 330px;
    @media(max-width: 1240px) {
      min-height: auto;
    }
    &__ico {
      box-shadow: var(--shadow);
      display: inline-block;
      border-radius: var(--shadowRadius);
      width: 65px;
      height: 65px;
      position: relative;
      margin-bottom: 20px;
      img {
        position: absolute;
        left: 50%;
        top: 50%;
        transform: translate(-50%, -50%);
      }
    }
    &__description {
      margin-top: auto;
      color: var(--text);
      font-size: 26px;
      font-weight: 700;
      line-height: 140%;
      @media(max-width: 1240px) {
        font-size: 20px;
      }
      @media(max-width: 767px) {
        font-size: 18px;
      }
    }
  }

</style>