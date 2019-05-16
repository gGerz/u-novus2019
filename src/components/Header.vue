<template>
  <div>
    <div>

    </div>
    <div class="menu d-flex align-item-center px-5 pb-3">
      <div class="logo my-auto">
        <img src="../assets/logo.png" class="logo" alt="logo">
      </div>
      <div class="pl-4">
        <img src="../assets/sw.jpg" class="smart" alt="logo">
      </div>
    </div>
    <div class="pl-5 d-flex header">
      <div>Карты</div>
      <div>Кредиты</div>
      <div>Вклады и инвестиции</div>
      <div>Консультант</div>
    </div>
  </div>
</template>
<style lang="scss">
  .header div {
    height: 70px;
    padding: 25px 15px;
    font-size: 18px;
    cursor: pointer;

      &:hover {
      border-bottom: 2px solid #266dc2;
    }
  }

  .menu{
    border-bottom: 3px solid lightgrey;
    padding-top: 30px;
    .logo {
      width: 250px;
    }
    .logo {

    }
    .smart {
      height: 65px;
    }
  }


</style>
