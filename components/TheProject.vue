<template>
  <div class="project">
    <div class="container">
      <div class="project__inner">
        <div class="project__title title">Запустим проект<span class="text-gradient">быстро, эффективно, с&nbsp;гарантией</span></div>
        <div class="project__list">
          <div
            v-for="(item, i) in card"
            :key="i" 
            class="project__item project-card">
            <div class="project-card__img">
              <img :src="item.ico" alt="svg">
            </div>
            <div class="project-card__info">
              <div class="project-card__title">{{ item.title }}</div>
              <div class="project-card__text">{{ item.text }}</div>
            </div>
          </div>
        </div>
        <div class="project__btn"><UITheButton :label="'Обсудить ваш проект'" class="btn btn-dark" /></div>
      </div>
      <TheTags />
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
        ico: (await import("@/assets/img/svg/item4.svg")).default,
        title: 'Платформа',
        text: 'Разработка и кастомизация готовых B2B- и B2C-решений на базе eCom платформы Кипу под потребности бизнеса. Быстрый запуск MVP от 2-4 месяцев',
      },
      {
        ico: (await import("@/assets/img/svg/item19.svg")).default,
        title: 'Экспертиза',
        text: 'Команда Кипу состоит из экспертов в области разработки eCom решений, практический опыт каждого из членов команды составляет более 10 лет, а общая насмотренность превышает 250 проектов',
      },
      {
        ico: (await import("@/assets/img/svg/item36.svg")).default,
        title: 'Методология',
        text: 'Каждый наш проект начинается, прежде всего, с разработки бизнес-логики, на базе которой строится ИТ-система. Расчет экономической модели проекта происходит уже на этапе исследования',
      },
      {
        ico: (await import("@/assets/img/svg/item37.svg")).default,
        title: 'Команда',
        text: 'Реализуем проекты любой сложности за счет горизонтального масштабирования ресурсов разработки с помощью партнерской программы',
      },
   
    )
    this.card = cards
	}
}
</script>

<style lang="scss">
  .project {
    &__inner {
      margin-bottom: 100px;
      @media(max-width: 1023px) {
        margin-bottom: 60px;
      }
    }
    &__title {
      max-width: 50%;
      @media(max-width: 1240px) {
        max-width: 100%;
      }
      span {
        margin-left: 0.3em;
      }
    }
    &__list {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 65px 80px;
      margin: 60px 0 65px;
      @media(max-width: 1023px) {
        margin: 60px 0;
        grid-template-columns: 1fr;
        gap: 30px;
      }
    }
  }
  .project-card {
    display: grid;
    grid-template-columns: 65px 1fr;
    color: var(--text);
    gap: 30px;
    @media(max-width: 1023px) {
      gap: 20px;
    }
    &__img {
      width: 65px;
      height: 65px;
      display: block;
      position: relative;
      box-shadow: var(--shadow);
      border-radius: var(--shadowRadius);
      img {
        position: absolute;
        display: block;
        left: 50%;
        top: 50%;
        transform: translate(-50%, -50%);
      }
    }
    &__title {
      font-size: 30px;
      font-weight: 700;
      margin-bottom: 20px;
      @media(max-width: 1023px) {
        font-size: 18px;
      }
    }
    &__text {
      font-size: 16px;
      font-weight: 400;
      @media(max-width: 1023px) {
        font-size: 14px;
      }
    }
  }
</style>