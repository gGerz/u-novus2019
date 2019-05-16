<template>
  <div id="app">
    <Header />
    <Voice @nextStepApp="nextStepApp"  />
    <Card />
    <Respons :label="labelText" />
<!--    <Body />-->
  </div>
</template>

<script>
  import axios from 'axios'

  import Header from './components/Header'
  import Body from './components/Body'
  import Respons from './components/Respons'
  import Voice from './components/Voice'
  import Card from './components/Card'

  export default {
    components: {
      Header,
      Body,
      Respons,
      Voice,
      Card
    },
    name: 'app',
    data () {
      return {
        showResponse: '',
        labelText: 'Здесь будет ваш ответ'
      }
    },
    methods: {
      nextStepApp(){
        this.showResponse = true
        this.labelText = {
          text: 'Ваш остаток по балансу: 7687.78',
          step: 1
        }
      }
    }
  }
</script>

<style lang="scss">
  body {
    font-family: 'Roboto', sans-serif;

  }
  shadow-a {
    -webkit-box-shadow: 0px 5px 2px 0px rgba(61,61,61,1);
    -moz-box-shadow: 0px 5px 2px 0px rgba(61,61,61,1);
    box-shadow: 0px 5px 2px 0px rgba(61,61,61,1);
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
