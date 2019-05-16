<template>
  <div class="d-flex justify-content-center">
    <div class="resp_box">{{label.text}}</div>
    <button class="btn-success" v-if="label.step === 1">Взять кредит</button>
    <button class="btn-success" v-if="label.step === 1">Пополнить счет</button>
  </div>
</template>
<script>
  export default {
    props: ['label'],
    data () {
      return {
      }
    },
  }
</script>
<style>

  .resp_box {
    width: 700px;
    border: solid 2px #ccddec;
    padding: 10px 20px;
    margin-bottom: 30px;
    border-radius: 6px;
  }
</style>
