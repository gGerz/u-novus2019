<template>
  <div>
    <div class="dev-line my-4 mx-auto"></div>
    <div class="d-flex justify-content-center">
      <div class="resp_box">
<!--        <card v-if="label.step === 1" />-->
        <div v-if="label.step === 1" class="d-flex justify-content-center">
          <div class=" w-100">
            <div class="balance d-flex justify-content-between">
              <div class="">
                <div class="card_title">Visa classic<img class="visa ml-3" src="../assets/visa.jpg" alt=""></div>
                <div class="font14">
                  Дебетовая карта
                </div>
                <div class="font14">**** 0451, дествительно до 11/2020</div>
              </div>
              <div class="d-flex">
                <div class="font24">
                  1 736.69 Р
                </div>

              </div>

            </div>
            <button class="btn-resp mt-3">Взять кредит</button>
            <button class="btn-resp mt-3">Пополнить счет</button>
            <!--      <button class="btn-resp mt-3">Внести деньги на счет</button>-->

            <!--      <div class="card_line my-4"></div>-->
            <!--      <div class="balance d-flex justify-content-between">-->
            <!--        <div class="">-->
            <!--          <div class="card_title">Visa classic<img class="visa ml-3" src="../assets/visa.jpg" alt=""></div>-->
            <!--          <div class="font14">-->
            <!--            Кредитные карта-->
            <!--          </div>-->
            <!--          <div class="font14">**** 0451, дествительно до 11/2020</div>-->
            <!--        </div>-->
            <!--        <div class="d-flex">-->
            <!--          <div class="font24">-->
            <!--             419 420.69 Р-->
            <!--          </div>-->
            <!--        </div>-->
            <!--      </div>-->
            <!--      <div class="card_line my-4"></div>-->
            <!--      <div class="balance d-flex justify-content-between">-->
            <!--        <div class="">-->
            <!--          <div class="card_title">Visa classic<img class="visa ml-3" src="../assets/visa.jpg" alt=""></div>-->
            <!--          <div class="font14">-->
            <!--            Кредитная карта-->
            <!--          </div>-->
            <!--          <div class="font14">**** 3822, дествительно до 11/2020</div>-->
            <!--        </div>-->
            <!--        <div class="d-flex">-->
            <!--          <div class="font24">-->
            <!--            288 000.69 Р-->
            <!--          </div>-->
            <!--        </div>-->
            <!--      </div>-->
          </div>
        </div>

<!--        <div v-if="label.text !== ''" class="mb-3">{{label.text}}</div>-->
<!--        <button class="btn-resp" v-if="label.step === 1">Взять кредит</button>-->
<!--        <button class="btn-resp" v-if="label.step === 1">Пополнить счет</button>-->
        <div v-if="label.step === 2">
          <div class="row resp-table">
            <div class="col-2 pl-0">Оплата услуг</div>
            <div class="col-2">Счет списания</div>
            <div class="col-2">Получатель</div>
            <div class="col-2 ">Дата</div>
            <div class="col-2">Сумма</div>
            <div class="col-2">Кешбек</div>
          </div>
          <div class="dev-line-table mt-3"></div>
          <div class="row resp-table">
            <div class="col-2 my-auto pl-0">Покупка продуктов</div>
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
            <div class="col-2 my-auto pl-0">Покупка монитора</div>
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
          <div class="row resp-table">
            <div class="col-2 my-auto pl-0">Оплата интернета</div>
            <div class="col-2">
              <div>Visa</div>
              <div>**** 1337</div>
            </div>
            <div class="col-2 my-auto">Ростелеком</div>
            <div class="col-2 my-auto">
              <div>Сегодня 18:41</div>
            </div>
            <div class="col-2 my-auto">899,00 руб.</div>
            <div class="col-2 my-auto">9,00 руб.</div>
          </div>
        </div>
        <div v-if="label.step === 3">
          <div class="credit_title">
            Информация о кредите
          </div>
          <div class="step_item">
            <div>Дата следующего взноса</div><div>13.05.2019</div>
          </div>
          <div class="step_item">
            <div>Нужно внести</div><div>20 000,00 руб.</div>
          </div>
          <div class="step_item">
            <div>Остаток выплаты:</div><div>50 000,00 руб.</div>
          </div>
        </div>
        <button class="btn-resp mt-2" v-if="label.step === 3">Cделать взнос</button>
        <card v-if="label.step === 4" />
      </div>
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
  .credit_title {
    margin-bottom: 10px;
    font-size: 22px;
    display: inline-block;
    border-bottom: 2px solid #dfdfdf;
  }
  .dev-line-table {
    border-bottom: 2px solid #dfdfdf;
  }
  .dev-line {
    border-bottom: 2px solid #dfdfdf;
    max-width: 700px;
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
  .step_item {
    display: flex;
    div:first-child {
      width: 350px;
      font-weight: 300;
    }
  }
  .card_war {
    padding-top: 15px;
    width: 650px;
    font-size: 12px;
    color: #a0a0a0;
  }
  .card_title {
    font-size: 24px;
  }
  .font14 {
    font-size: 14px;
  }
  .font24 {
    font-size: 24px;
  }
  .visa {
    width: 40px;
  }
  .card_line {
    border-bottom: 2px solid #dfdfdf;
  }
</style>
