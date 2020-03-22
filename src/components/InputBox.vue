<template>
  <div class="input_wrap">
    <input type="text" v-model="inputValue" autofocus>
    <button type="submit">검색</button>
  </div>
</template>

<script>
export default {
  props: ['value'],
  data () {
    return {
      inputValue: this.value
    }
  }

}
</script>

<style>

</style>
