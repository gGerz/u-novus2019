<template>
  <div id="app">
    <div class="container">
      <div class="row">
        <div class="col-12">
          <div class="step__first">
            <h1>Поздоровайтесь с консультантом!</h1>
            <img class="micro" src="./assets/micro.png" alt="micro">
          </div>
        </div>
      </div>
      <div class="row justify-content-around">
        <button class="btn btn-warning">Отмена</button>
        <button class="btn btn-success">Следующий вопрос</button>
      </div>
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
      msg: 'Welcome to Your Vue.js App'
    }
  }
}
</script>

<style lang="scss">
  .micro{
    height: 150px;
    width: 150px;
  }

  .step__first{
    display: flex;
    align-items: center;
    flex-direction: column;
  }

  .btn{
    height: 150px;
    width: 150px;
    border-radius: 150px;
  }
</style>
