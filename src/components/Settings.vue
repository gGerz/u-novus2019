<template>
  <div>
    <!-- Button trigger modal -->
    <button type="button" class="btn btn-primary" data-toggle="modal" data-target="#exampleModalCenter">
      S
    </button>

    <!-- Modal -->
    <div class="modal fade" id="exampleModalCenter" tabindex="-1" role="dialog" aria-labelledby="exampleModalCenterTitle" aria-hidden="true">
      <div class="modal-dialog modal-lg modal-dialog-centered" role="document">
        <div class="modal-content">
          <div class="modal-header">
            <h5 class="modal-title" id="exampleModalLongTitle">Настройка эмпатической связи</h5>
            <button type="button" class="close" data-dismiss="modal" aria-label="Close">
              <span aria-hidden="true">&times;</span>
            </button>
          </div>
          <div class="modal-body ">
            <div class="mx-auto w-75">
              <div class="mb-4">
                Отавьте образец голоса для более эффективного взаимодействия
                <img src="../assets/micro.png" class="set_mic" alt="">
              </div>
              <div class="mb-4">
                Настроить голос помощника
                <select class="form-control" id="exampleFormControlSelect1">
                  <option>Женский нейтральный</option>
                  <option>Женский мягкий</option>
                  <option>Женский игривый</option>
                  <option>Женский застенчивый</option>
                  <option>Женский холодный</option>
                </select>
              </div>
              <div>Как к вам обращаться?</div>
              <input type="text" class="form-control" id="validationServer01" placeholder="First name" value="Семпай" required>
            </div>
          </div>
          <div class="modal-footer">
            <button type="button" class="btn btn-primary" data-dismiss="modal">Сохранить</button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<style>
  .set_mic {
    width: 35px;
  }
</style>
