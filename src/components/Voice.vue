<template>
  <div class="mt-5 d-flex justify-content-center">
    <div>
      <div class="d-flex main-voice">
        <input type="text"  v-model="query" class="" id="exampleInputEmail1" aria-describedby="emailHelp" placeholder="Нажмите на кнопку и задайте вопрос ...">
        <button @click="nextStep" class="btn btn-primary btn-micro">
          <i class="fas fa-microphone"></i>
        </button>
      </div>

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
        this.$store.state.loader = true
        setTimeout(this.setQueryText, 5000)
      },
      setQueryText(){
        if (this.query === ''){
          this.$emit('nextStepApp')
          this.query = 'Оcтаток по балансу'
          this.$store.state.loader = false
          return
        }
        if (this.query === 'Оcтаток по балансу'){
          this.$emit('nextStepApp')
          this.query = 'Выписка последних операций'
          this.$store.state.loader = false
          return
        }
        if (this.query === 'Выписка последних операций'){
          this.$emit('nextStepApp')
          this.query = 'Дата оплаты по кредиту'
          this.$store.state.loader = false
          return
        }
        if (this.query === 'Дата оплаты по кредиту'){
          this.$emit('nextStepApp')
          this.query = 'Остаток по кредитной карте'
          this.$store.state.loader = false
          return
        }
      }
    },
    mounted(){
    }
  }
</script>

<style lang="scss">
  .dev-line {
    border-bottom: 2px solid #dfdfdf;
  }
  .main-voice {
    font-size: 22px;
    height: 60px;
    width: 700px!important;
    input {
      width: 100%;
      border-radius: 6px;
      border: solid 2px #ccddec;
      padding: 0px 20px;
      border-bottom-right-radius: 0px;
      border-top-right-radius: 0px;
      border-right: 0px;
    }
    .micro {
      position: absolute;
      height: 60px;
      width: auto;
    }
  }
  .btn-micro {
    height: auto!important;
    background: #266dc2!important;
    width: 70px;
    font-size: 25px;
    border-bottom-left-radius: 0px;
    border-top-left-radius: 0px;
  }
</style>
