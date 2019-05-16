<template>
  <div class="d-flex justify-content-center">
    <div class="resp_box">
      <div class="mb-3">{{label.text}}</div>
      <button class="btn-resp" v-if="label.step === 1">Взять кредит</button>
      <button class="btn-resp" v-if="label.step === 1">Пополнить счет</button>
      <div>12123</div>
    </div>
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
<style lang="scss">
  .btn-resp {
    font-size: 16px;
    background: #266dc2;
    color: white;
    border: none;
    border-radius: 4px;
    padding: 8px 18px;
    &:hover {
      background: #2262ae;
    }
  }
  .resp_box {
    width: 700px;
    border: solid 2px #ccddec;
    padding: 16px 30px;
    margin-bottom: 30px;
    border-radius: 6px;
    font-size: 20px;
  }
</style>
