<template>
<div class="page">
  <h2 class="title page__title">Текст перед полем ввода</h2>
  <FormInput />
</div>
</template>

<script>
import FormInput from './components/FormInput.vue'

export default {
  name: 'App',
  components: {
    FormInput
  }
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #303030;;
  margin-top: 60px;
  padding: 0 30px;
}
.page {
  &__title {
    font-size: 18px;
  }
}
</style>
