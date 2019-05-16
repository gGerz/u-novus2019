<template>
  <div id="app">
    <Header />
    <div class="container">
      <div class="row">
        <div class="col-12">
          <div class="steps">
            <div class="step step__first" v-if="firstStep">
              <h1>Поздоровайтесь с консультантом!</h1>
              <img class="micro" src="./assets/micro.png" alt="micro">
            </div>
            <div class="step step__second" v-if="secondStep">
              <h1>Приветики!</h1>
            </div>
          </div>
        </div>
      </div>
      <div class="row justify-content-around">
        <button class="btn btn-cancel">Отмена</button>
        <button class="btn btn-next" @click="nextSecondStep()">Спросить еще</button>
      </div>
    </div>

  </div>
</template>

<script>
  import axios from 'axios'

  import Header from './components/Header'

  export default {
    components: {
      Header
    },
    name: 'app',
    data () {
      return {
        firstStep: true,
        secondStep: false,
      }
    },
    methods: {
      nextSecondStep(){
        this.firstStep = false
        this.secondStep = true
      }
    }
  }
</script>

<style lang="scss">
  body {
    font-family: sans-serif;
  }
  .micro{
    height: 150px;
    width: 150px;
  }

  .step{
    display: flex;
    align-items: center;
    flex-direction: column;
  }

  .btn{
    width: 250px;
    height: 75px;
  }

  .btn-cancel{
    border: 1px solid #498dde;
    color: #266dc2;

    &:hover{
      background-color: #f5faff;
      color: #266dc2;
    }
  }
  .btn-next{
    background-color: #00549E;
    color: #ffffff;

    &:hover{
      background-color: #2869ca;
      color: #ffffff;
    }
  }
</style>
