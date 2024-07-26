<template>
  <button
    :type="type"
    class="btn"
  >
    <span v-if="svg" v-html="svg"></span>
    {{ label }}
  </button>
</template>

<script>
export default {
  props: {
    label: {
      label: String,
      default: '',
      require: true
    },
    type: {
      type: String,
      dafault: ''
    },
    svg: {
      type: String,
      dafault: ''
    }
  }
}
</script>

<style lang="scss">
  .btn {
    border: solid 1px transparent;
    cursor: pointer;
    transition: 0.3s;
    display: inline-block;
    border-radius: 10px;
    font-size: 16px;
    font-weight: 700;
    &:active {
      @media(max-width: 1023px) {
        background-color: tomato;
      }
    } 
  }
  .btn-dark {
    background-color: var(--darkBlue);
    color: var(--white);
    padding: 18px 30px;
    &:hover {
      @media(min-width: 1023px) {
        background: var(--darkBlueHover);
      }
    }
  }
  .btn-light {
    background-color: var(--white);
    color: var(--text);
    border: solid 1px transparent;
    padding: 18px 53px;
    &:hover {
      @media(min-width: 1023px) {
        background: var(--whiteHover);
      }
    }
  }
</style>