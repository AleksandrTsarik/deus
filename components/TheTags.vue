<template>
  <div class="tags">
    <div class="tags__title title"><span class="text-gradient">Какие задачи</span>решаем в eCommerce</div>
    <div class="tags__list">
      <NuxtLink
        v-for="(item, i) in tags"
        :key="i"
        :to="item.url"
        class="tag">{{ item.name }}</NuxtLink>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      tags: [
        {
          name: 'Автоматизация бизнес-процессов',
          url: '#'
        },
        {
          name: 'Создание B2B-портала',
          url: '#'
        },
        {
          name: 'Разработка интернет-магазина',
          url: '#'
        },
        {
          name: 'Управление товарными данными',
          url: '#'
        },
        {
          name: 'Маркетинговые активности',
          url: '#'
        },
        {
          name: 'Интеграция с маркетплейсами',
          url: '#'
        },
        {
          name: 'Медиа-контент',
          url: '#'
        },
        {
          name: 'Управление отзывами',
          url: '#'
        },
        {
          name: 'Работа с заказами',
          url: '#'
        },
        {
          name: 'Доставка и возвраты',
          url: '#'
        },
        {
          name: 'Остатки и ценообразование',
          url: '#'
        },
        {
          name: 'Взаимоотношения с клиентами',
          url: '#'
        },
        {
          name: 'Аналитика',
          url: '#'
        },
        {
          name: 'Нишевые маркетплейсы',
          url: '#'
        },
        {
          name: 'Обмен данными',
          url: '#'
        }
      ]
    }
  }
}
</script>

<style lang="scss">
  .tags {
    border-radius: 20px;
    box-shadow: 15px 10px 30px 0px rgba(210, 218, 227, 0.7),5px 5px 13px 0px rgba(210, 218, 227, 0.3),-5px -5px 10px 0px rgb(255, 255, 255),-20px -20px 34px 0px rgba(255, 255, 255, 0.8);
    padding: 80px;
    @media(max-width: 1023px) {
      padding: 60px 0;
      border-radius: 0;
      box-shadow: none;
    }
    &__title {
      margin-bottom: 60px;
      @media(max-width: 1023px) {
        margin-bottom: 40px;
      }
      span {
        margin-right: 0.3em;
      }
    }
    &__list {
      display: flex;
      flex-wrap: wrap;
      @media(max-width: 1023px) {
        flex-wrap: nowrap;
        width: 100%;
        overflow-x: auto;
      }
    }
  }
  .tag {
    color: var(--text); 
    border-radius: 10px;
    box-shadow: 7px 7px 30px 0px rgba(210, 218, 227, 0.6),5px 5px 13px 0px rgba(210, 218, 227, 0.3),-5px -5px 10px 0px rgb(255, 255, 255),-10px -10px 34px 0px rgba(255, 255, 255, 0.8);
    margin: 0 25px 25px 0;
    padding: 18px 30px;
    font-size: 16px;
    font-weight: 700;
    white-space: nowrap;
  }
</style>