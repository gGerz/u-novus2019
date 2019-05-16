<template>
  <div id="app">
    <Header />

    <Voice @nextStepApp="nextStepApp"  />
    <!--<Card />-->
    <Respons v-if="showResponse && !$store.state.loader" :label="labelText" />
    <span v-if="$store.state.loader" class="ouro">
      <span class="left"><span class="anim"></span></span>
      <span class="right"><span class="anim"></span></span>
    </span>

    <div class="btn-panel">
      <Settings />
    </div>

    <!-- Modal -->
    <div class="modal fade" id="exampleModalCenter" tabindex="-1" role="dialog" aria-labelledby="exampleModalCenterTitle" aria-hidden="true">
      <div class="modal-dialog modal-lg modal-dialog-centered" role="document">
        <div class="modal-content">
          <div class="modal-header">
            <h5 class="modal-title" id="exampleModalLongTitle">Настройка эмпатической связи</h5>
            <button type="button" class="close" data-dismiss="modal" aria-label="Close">
              <span aria-hidden="true">&times;</span>
            </button>
          </div>
          <div class="modal-body ">
            <div class="mx-auto w-75">
              <div class="mb-4 d-flex justify-content-between align-item-center">
                <div class="my-auto">
                  Отавьте образец голоса для более эффективного взаимодействия
                </div>
                <div>
                  <img src="./assets/micro.png" class="set_mic" alt="">
                </div>
              </div>
              <div class="mb-4">
                Настроить голос помощника
                <select class="form-control" id="exampleFormControlSelect1">
                  <option>Женский нейтральный</option>
                  <option>Женский мягкий</option>
                  <option>Женский игривый</option>
                  <option>Женский застенчивый</option>
                  <option>Женский холодный</option>
                </select>
              </div>
              <div>Как к вам обращаться?</div>
              <input type="text" class="form-control" id="validationServer01" placeholder="First name" value="Семпай" required>
            </div>
          </div>
          <div class="modal-footer">
            <button type="button" class="btn btn-primary" data-dismiss="modal">Сохранить</button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
  import axios from 'axios'

  import Header from './components/Header'
  import Body from './components/Body'
  import Respons from './components/Respons'
  import Voice from './components/Voice'
  import Card from './components/Card'
  import Settings from './components/Settings'

  export default {
    components: {
      Header,
      Body,
      Respons,
      Voice,
      Card,
      Settings
    },
    name: 'app',
    data () {
      return {
        showLoader: false,
        showResponse: false,
        labelText: 'start'
      }
    },
    methods: {
      nextStepApp(){
        this.showResponse = true
        if (this.labelText === 'start'){
          this.labelText = {
            text: 'Ваш остаток по балансу: 7687.78',
            step: 1
          }
          return
        }
        if (this.labelText.step === 1){
          this.labelText = {
            text: 'Ваши последние 10 операций',
            step: 2
          }
          return
        }
        if (this.labelText.step === 2){
          this.labelText = {
            text: 'Дата следующего взноса',
            step: 3
          }
          return
        }
        if (this.labelText.step === 3){
          this.labelText = {
            text: '',
            step: 4
          }
          return
        }
      }
    }
  }
</script>

<style lang="scss">
  .btn-panel {
    position: fixed;
    right: 20px;
    bottom: 20px;
  }
  .ouro {
    position: absolute;
    right: 50%;
    height: 46px;
    width: 46px;
    margin: 1em;
    border-radius: 50%;
    background: none repeat scroll 0 0 #DDDDDD;
    overflow:hidden;
    box-shadow: 0 0 10px rgba(0,0,0,.1) inset, 0 0 25px rgba(0,0,255,0.075);
  }

  .ouro:after {
    content: "";
    position: absolute;
    top: 9px; left: 9px;
    display: block;
    height: 28px; width: 28px;
    background: none repeat scroll 0 0 #F2F2F2;
    border-radius: 50%;
    box-shadow: 0 0 10px rgba(0,0,0,.1);
  }
  .ouro > span {
    position: absolute;
    height: 100%; width: 50%;
    overflow: hidden;
  }
  .left  { left:0   }
  .right { left:50% }

  .anim {
    position: absolute;
    left: 100%; top: 0;
    height: 100%; width: 100%;
    border-radius: 999px;
    background: none repeat scroll 0 0 #508EC3;
    opacity: 0.8;
    -webkit-animation: ui-spinner-rotate-left 3s infinite;
    animation: ui-spinner-rotate-left 3s infinite;
    -webkit-transform-origin: 0 50% 0;
    transform-origin: 0 50% 0;
  }
  .left .anim {
    border-bottom-left-radius: 0;
    border-top-left-radius: 0;
  }
  .right .anim {
    border-bottom-right-radius: 0;
    border-top-right-radius: 0;
    left: -100%;
    -webkit-transform-origin: 100% 50% 0;
    transform-origin: 100% 50% 0;
  }
  @keyframes ui-spinner-rotate-right{
    0%{transform:rotate(0deg)}
    25%{transform:rotate(180deg)}
    50%{transform:rotate(180deg)}
    75%{transform:rotate(360deg)}
    100%{transform:rotate(360deg)}
  }
  @keyframes ui-spinner-rotate-left{
    0%{transform:rotate(0deg)}
    25%{transform:rotate(0deg)}
    50%{transform:rotate(180deg)}
    75%{transform:rotate(180deg)}
    100%{transform:rotate(360deg)}
  }

  @-webkit-keyframes ui-spinner-rotate-right{
    0%{-webkit-transform:rotate(0deg)}
    25%{-webkit-transform:rotate(180deg)}
    50%{-webkit-transform:rotate(180deg)}
    75%{-webkit-transform:rotate(360deg)}
    100%{-webkit-transform:rotate(360deg)}
  }
  @-webkit-keyframes ui-spinner-rotate-left{
    0%{-webkit-transform:rotate(0deg)}
    25%{-webkit-transform:rotate(0deg)}
    50%{-webkit-transform:rotate(180deg)}
    75%{-webkit-transform:rotate(180deg)}
    100%{-webkit-transform:rotate(360deg)}
  }
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
