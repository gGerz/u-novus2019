<template>
  <div>
    <!-- Button trigger modal -->
    <div class="my-1" >
      <button type="btn" class="set_btn" data-toggle="modal" data-target="#exampleModalCenter">
        <i class="fas fa-cog"></i>
      </button>
    </div>
    <div  class="my-1">
      <button type="btn" class="set_btn" data-toggle="modal" data-target="#exampleModalCenter">
        ?
      </button>
    </div>
    <div class="my-1">
      <button type="btn" class="set_btn" data-toggle="modal" data-target="#exampleModalCenter">
        <i class="far fa-keyboard"></i>
      </button>
    </div>

  </div>
</template>
<style lang="scss">
  .set_mic {
    width: 40px;
    height: auto;
  }
  .set_btn {
    background: #b8b8b8;
    border: none;
    color: white;
    width: 70px;
    height: 70px;
    font-size: 40px;
    border-radius: 100px;
    box-shadow: none;
    &:focus {
       outline: 0;
       box-shadow: 0 0 0 0.2rem rgba(0,123,255,.25);
     }
  }
</style>
