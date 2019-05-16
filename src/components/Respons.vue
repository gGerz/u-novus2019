<template>
  <div class="d-flex justify-content-center">
    <div class="resp_box">
      <div v-if="label.text !== ''" class="mb-3">{{label.text}}</div>
      <button class="btn-resp" v-if="label.step === 1">Взять кредит</button>
      <button class="btn-resp" v-if="label.step === 1">Пополнить счет</button>
      <div v-if="label.step === 2">
        <div class="row resp-table">
          <div class="col-2">Оплата услуг</div>
          <div class="col-2">Счет списания</div>
          <div class="col-2">Получатель</div>
          <div class="col-2 ">Дата</div>
          <div class="col-2">Сумма</div>
          <div class="col-2">Кешбек</div>
        </div>
        <div class="dev-line mt-3"></div>
        <div class="row resp-table">
          <div class="col-2 my-auto">Купил покушать</div>
          <div class="col-2">
            <div>Visa</div>
            <div>**** 1337</div>
          </div>
          <div class="col-2 my-auto">Пятерочка</div>
          <div class="col-2 my-auto">
            <div>Сегодня 18:00</div>
          </div>
          <div class="col-2 my-auto">1 999,00 руб.</div>
          <div class="col-2 my-auto">5,00 руб.</div>
        </div>
        <div class="row resp-table">
          <div class="col-2 my-auto">Купил моник</div>
          <div class="col-2">
            <div>Visa</div>
            <div>**** 1337</div>
          </div>
          <div class="col-2 my-auto">DNC</div>
          <div class="col-2 my-auto">
            <div>Сегодня 18:01</div>
          </div>
          <div class="col-2 my-auto">9 999,00 руб.</div>
          <div class="col-2 my-auto">9,00 руб.</div>
        </div>
      </div>
      <div v-if="label.step === 3">
        Вам нужно внести: 20000. Остаток выплаты по кредиту: 40000.
      </div>
      <button class="btn-resp" v-if="label.step === 3">Cделать взнос</button>
      <card v-if="label.step === 4" />
    </div>
  </div>
</template>
<script>
  import Card from '../components/Card'
  export default {
    components: {
      Card
    },
    props: ['label'],
    data () {
      return {
      }
    },
  }
</script>
<style lang="scss">
  .dev-line {
    border-bottom: 2px solid #dfdfdf;
  }
  .resp-table {
    margin: 20px 0px;
    font-size: 16px;
    width: 1000px;
  }
  .btn-resp {
    font-size: 16px;
    background: #266dc2;
    color: white;
    border: none;
    border-radius: 4px;
    padding: 8px 18px;
    &:hover {
      background: #2262ae;
    }
  }
  .resp_box {
    min-width: 700px;
    border: solid 2px #ccddec;
    padding: 16px 30px;
    margin-bottom: 30px;
    border-radius: 6px;
    font-size: 20px;
  }
</style>
