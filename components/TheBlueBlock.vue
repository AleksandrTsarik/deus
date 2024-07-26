<template>
  <div class="blue-block r-40">
    <div class="blue-block__info">
      <div class="blue-block__title">{{ title }}</div>
      <div class="blue-block__text">{{ row }}</div>
    </div>
    <div class="blue-block__btn">
      <UITheButton :label="'Получить бесплатно'" class="btn btn-light" />
    </div>
  </div>
</template>

<script>
export default {
  props: {
    title: {
      type: String,
      default: ''
    },
    row: {
      type: String,
      default: ''
    }
  }
}
</script>

<style lang="scss">
  .blue-block {
    background: linear-gradient(137.70deg, rgb(57, 199, 236) 4.565%,rgb(57, 199, 236) 4.575%,rgb(0, 80, 236) 96.443%);
    padding: 60px 75px;
    color: var(--white);
    display: grid;
    grid-template-columns: 1fr 0.5fr;
    align-items: center;
    gap: 20px;
    @media(max-width: 1240px) {
      grid-template-columns: 1fr 0.8fr;
    }
    @media(max-width: 1023px) {
      grid-template-columns: 1fr;
      padding: 60px 15px;
    }
    &__info {}
    &__title {
      font-size: 40px;
      font-weight: 700;
      line-height: 120%;
      margin-bottom: 20px;
      @media(max-width: 767px) {
        font-size: 22px;
      }
    }
    &__text {
      font-size: 18px;
      font-weight: 400;
      line-height: 140%;
      @media(max-width: 767px) {
        font-size: 14px;
      }
    }
    &__btn {
      margin-left: auto;
      @media(max-width: 1023px) {
        margin: 0;
      }
    }
  }
</style>