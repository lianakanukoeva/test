<template>
  <div class="hello">
    <h2>введите текст</h2>
    <form>
      <!-- <input type="text" name="" id=""> -->
      <textarea name="" id="" cols="30" rows="10" v-model="count"></textarea>
    <div v-if="count.length > 1000">Ошибка</div>
    <div class="counter">{{ count.length }}/1000</div>
      <button @click.prevent="count=''">Очистить</button>
    </form>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data() {
    return {
      count: ''
    }
  }
}
</script>

<style scoped lang="scss">
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
