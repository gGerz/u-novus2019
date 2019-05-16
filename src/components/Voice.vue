<template>
  <div class="mt-5 d-flex justify-content-center">
    <div>
      <div class="d-flex main-voice">
        <input type="text"  v-model="query" class="" id="exampleInputEmail1" aria-describedby="emailHelp" placeholder="Нажмите на кнопку и задайте вопрос ...">
        <button @click="nextStep" class="btn btn-primary btn-micro">
          <i class="fas fa-microphone"></i>
        </button>
      </div>
      <div class="dev-line my-4"></div>
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
          return
        }
        if (this.query === 'Оcтаток по балансу'){
          this.$emit('nextStepApp')
          this.query = 'Выписка последних операций'
          return
        }
        if (this.query === 'Выписка последних операций'){
          this.$emit('nextStepApp')
          this.query = 'Дата оплаты по кредиту'
          return
        }
        if (this.query === 'Дата оплаты по кредиту'){
          this.$emit('nextStepApp')
          this.query = 'Сведения по кредиту'
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
