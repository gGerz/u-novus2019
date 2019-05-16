<template>
  <div class="container body-container">
    <div class="row">
      <div class="col-12">
        <div class="steps">
          <div class="step step__first" v-if="firstStep">
            <h1>Голосой помощник SmartWorld</h1>
            <div class="d-flex main-voice">
              <input type="text" class="" id="exampleInputEmail1" aria-describedby="emailHelp" placeholder="Скажите что-нибудь...">
              <img class="micro" @click="nextSecondStep()" src="../assets/micro.png" alt="micro">
            </div>

            <div class="d-flex main-voice-b">
              <input type="text" class="" id="exampleInputEmail1" aria-describedby="emailHelp" placeholder="Скажите что-нибудь...">
              <button class="btn btn-primary btn-micro">
                <i class="fas fa-microphone"></i>
              </button>
            </div>
            <div class="resp_box balance">
              <div class="  ">
                <div>
                  Ваше имя
                </div>
                <input type="text" class="form-input" id="formGroupExampleInput" placeholder="Example input">
              </div>
              <div class="form-group">
                <label for="formGroupExampleInput2">Another label</label>
                <input type="text" class="form-control" id="formGroupExampleInput2" placeholder="Another input">
              </div>
            </div>
            <div class="resp_box balance">
              <div>
                Зарплатная карта
              </div>
              <div>
                1 337 000.69 Р
              </div>
              <div class="d-flex justify-content-between">
                <div>**** 5028</div>
                <div> VISA</div>
              </div>
            </div>
            <div class="resp_box">
              Оплатите кредит до 13 июня
            </div>
          </div>
          <div class="step step__second" v-if="secondStep">
            <h1>Приветики!</h1>
          </div>
        </div>
      </div>
    </div>
    <div class="row justify-content-around" v-if="!firstStep">
      <button class="btn btn-cancel">Отмена</button>
      <button class="btn btn-next" @click="nextSecondStep()">Спросить еще</button>
    </div>
  </div>
</template>
<script>
  export default {
    components: {
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
  .resp_box {
    width: 700px;
    border: solid 2px #ccddec;
    padding: 10px 20px;
    margin-bottom: 30px;
    border-radius: 6px;
  }
  .balance {
  }
  .main-voice-b {
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
      left: 0px
    }
  }
  .btn-micro {
    height: auto!important;
    width: 70px;
  }
  .main-voice {
    margin-bottom: 30px;
    font-size: 22px;
    height: 60px;
    width: 700px!important;
    input {
      width: 100%;
      border-radius: 100px;
      border: 2px #5d5d5d solid;
      padding: 0px 30px;
    }
    img {
      height: 100%;
      width: auto;
    }
  }
  .body-container {

  }
</style>
