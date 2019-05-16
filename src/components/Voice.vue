<template>
  <div class="d-flex justify-content-center">
    <div class="d-flex main-voice">
      <input type="text" class="" id="exampleInputEmail1" aria-describedby="emailHelp" placeholder="Скажите что-нибудь...">
      <button class="btn btn-primary btn-micro">
        <i class="fas fa-microphone"></i>
      </button>
    </div>
  </div>
</template>

<style lang="scss">
  .main-voice {
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
    }
  }
  .btn-micro {
    height: auto!important;
    width: 70px;
  }
</style>
