<template>
  <div class="container">
    <div class="row">
      <div class="col-12">
        <div class="steps">
          <div class="step step__first" v-if="firstStep">
            <h1>Голосой помощник SmartWorld</h1>
            <div class="form-group">
              <input type="text" class="form-control" id="exampleInputEmail1" aria-describedby="emailHelp" placeholder="Скажите что-нибудь...">
              <img class="micro" @click="nextSecondStep()" src="../assets/micro.png" alt="micro">
            </div>
            <div class="resp_box balance">
              <div>
                Зарплатная карта
              </div>
              <div>
                1 337 000.69 Р
              </div>
              <div>**** 5028</div>
              <div> VISA</div>
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
<style>
  .resp_box {
    border: 2px #5d5d5d dashed;
    border-radius: 10px;
    padding: 10px 20px;
  }
  .balance {
    width: 450px;
    height: 200px;
  }
</style>
