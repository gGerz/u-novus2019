<template>
  <div>
    <div class="menu d-flex justify-content-center align-item-center px-5 pb-3">
      <div class="logo my-auto">
        <img src="../assets/logo.png" class="logo" alt="logo">
      </div>
      <div class="pl-4">
        <img src="../assets/sw.jpg" class="smart" alt="logo">
      </div>
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
    /*border-bottom: 3px solid lightgrey;*/
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
