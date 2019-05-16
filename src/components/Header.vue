<template>
  <div>
    <div class="menu">
      <img src="../assets/logo.png" class="logo" alt="logo">
    </div>
    <div class="d-flex header">
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
      border-bottom: 3px solid #266dc2;
    }
  }

  .menu{
    border-bottom: 3px solid lightgrey;

    .logo{
      padding: 15px;
      margin-top: 10px;
      width: 250px;
    }
  }


</style>
