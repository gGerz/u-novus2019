<template>
  <div class="mt-5 d-flex justify-content-center">
    <div class="d-flex main-voice">
      <input type="text" disabled v-model="query" class="" id="exampleInputEmail1" aria-describedby="emailHelp" placeholder="Нажмите на кнопку и задайте вопрос ...">
      <button @click="nextStep" class="btn btn-primary btn-micro">
        <i class="fas fa-microphone"></i>
      </button>
    </div>
  </div>
</template>

<script>
  export default{
    data(){
      return {
        query: ''
      }
    },
    methods: {
      nextStep(){
        setTimeout(this.setQueryText, 5000)
      },
      setQueryText(){
        this.$emit('nextStepApp')
        this.query = 'Хочу узнать свой баланс'
      }
    },
    mounted(){
    }
  }
</script>

<style lang="scss">
  .main-voice {
    margin-bottom: 30px;
    font-size: 22px;
    height: 60px;
    width: 700px!important;
    input {
      width: 100%;
      border-radius: 6px;
      border: solid 2px #ccddec;
      padding: 0px 20px;
    }
    .micro {
      position: absolute;
      height: 60px;
      width: auto;
    }
  }
  .btn-micro {
    height: auto!important;
    width: 70px;
  }
</style>
