<template>
    <form class="form page__form">
      <div class="form__input" :class="{ form__input_error: count.length > 1000 }">
        <textarea class="form__textarea" placeholder=" " v-model="count"></textarea>
        <label class="form__label">Название поля</label>
        <div class="form__load">
          <svg class="spinner" viewBox="0 0 50 50">
            <circle class="path" cx="25" cy="25" r="20" fill="none" stroke-width="5"></circle>
          </svg>
        </div>
      </div>
      <div class="form__error" v-if="count.length > 1000">Ошибка</div>
      <div class="form__counter">{{ count.length }}/1000</div>
      <button class="form__button" @click.prevent="count=''">Очистить</button>
    </form>
</template>

<script>
export default {
  name: 'FormInput',
  data() {
    return {
      count: ''
    }
  }
}
</script>

<style scoped lang="scss">
.form {
  font-size: 14px;
  line-height: 20px;
  &__input{
    position: relative;
    max-width: 326px !important;
    max-height: 146px;
    padding: 20px 32px 16px 12px;
    margin-bottom: 8px;
    background-color: #f0f0f0;
    border-radius: 8px;
    &_error {
      background-color: #FBF0EF;
    }
  }
  &__textarea {
    width: 100%;
    height: 110px;
    padding: 0;
    padding-top: 4px;
    background: 0;
    font-family: Arial, Helvetica, sans-serif;
    font-size: 16px;
    outline: none;
    border: 0;
    line-height: 22px;
    letter-spacing: 0.5px;
    resize: none;
  }
  &__label{
    position: absolute;
    top: 12px;
    left: 12px;
    z-index: 0;
    font-size: 16px;
    color: #8C8C8C;
    transition: 0.2s;
    pointer-events: none;
  }
  &__textarea:focus ~ &__label,
  &__textarea:not(:placeholder-shown) ~ &__label{
    top: 4px;
    font-size: 12px;
  }
  &__load {
    position: absolute;
    width: 20px;
    height: 20px;
    top: 7px;
    right: 7px;
    animation: 1s linear infinite load;
    svg circle {
      stroke: #00B6D0;
      stroke-linecap: round;
      stroke-dasharray: 75, 100;
    }
  }
  &__error {
    color: #D6675C;
  }
  &__button {
    border: none;
    outline: none;
    color: #00B6D0;
    background: none;
    padding: 0;
    &:hover {
      cursor: pointer;
      color: blue;
    }
  }
  &__counter {
    color: #878F97;
  }
  @keyframes load{
      0% {transform: rotateZ(0deg);}
      100% {transform: rotateZ(360deg);}
  }
}
</style>
