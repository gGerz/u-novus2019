<template>
  <div id="app">
    <Header />
    <Body />
<!--    <div class="container">-->
<!--      <div class="row">-->
<!--        <div class="col-12">-->
<!--          <div class="steps">-->
<!--            <div class="step step__first" v-if="firstStep">-->
<!--              <h1>Голосой помощник SmartWorld</h1>-->
<!--              <div class="form-group">-->
<!--                <input type="text" class="form-control" id="exampleInputEmail1" aria-describedby="emailHelp" placeholder="Скажите что-нибудь...">-->
<!--                <img class="micro" @click="nextSecondStep()" src="./assets/micro.png" alt="micro">-->
<!--              </div>-->
<!--            </div>-->
<!--            <div class="step step__second" v-if="secondStep">-->
<!--              <h1>Приветики!</h1>-->
<!--            </div>-->
<!--          </div>-->
<!--        </div>-->
<!--      </div>-->
<!--      <div class="row justify-content-around" v-if="!firstStep">-->
<!--        <button class="btn btn-cancel">Отмена</button>-->
<!--        <button class="btn btn-next" @click="nextSecondStep()">Спросить еще</button>-->
<!--      </div>-->
<!--    </div>-->

  </div>
</template>

<script>
  import axios from 'axios'

  import Header from './components/Header'
  import Body from './components/Body'

  export default {
    components: {
      Header,
      Body
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

    h1{
      margin: 20px 0;
    }
  }

  .step__first{

    .form-group{
      display: flex;
      align-items: center;
      justify-content: center;
      width: 100%;

      input{
        max-width: 250px;
      }

      img{
        width: 50px;
        height: 50px;
        margin-left: 15px;
      }
    }
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
