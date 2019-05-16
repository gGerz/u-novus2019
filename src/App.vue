<template>
  <div id="app">
    <Header />
    <Voice />
    <Respons label="Вы не заплатили за кредит, колекторы уже в пути" />
<!--    <Body />-->
  </div>
</template>

<script>
  import axios from 'axios'

  import Header from './components/Header'
  import Body from './components/Body'
  import Respons from './components/Respons'
  import Voice from './components/Voice'

  export default {
    components: {
      Header,
      Body,
      Respons,
      Voice
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
    font-family: 'Roboto', sans-serif;
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
