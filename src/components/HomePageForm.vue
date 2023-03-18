<template>
  <!-- 表單區域 -->
  <div style="background-color:#E5E5E5; padding:100px 0 80px 0;">
    <form action="" class="container position-relative d-flex flex-column" id="form">
      <!-- 標題 -->
      <div class="rounded-5 border border-2 border-danger rounded-4 bg-white py-2 ps-4 pe-3 d-inline
       position-absolute start-50 translate-middle-x fw-bold text-danger"
        style="letter-spacing: 10px; top:-20px;">
       FORM
       <img src="../assets/images/turtle.png" class="position-absolute" alt=""
          style="z-index:1000; top:-20px; right:-40px">
      </div>
      <!-- 資料填寫區 -->
      <div class="bg-white border border-danger border-2 rounded pt-5 pb-3 px-3 mx-auto"
       style="max-width:800px;">
        <!-- 商店 -->
        <label for="store" class="form-label w-100">
          <span class="position-relative">
            store
            <span class="position-absolute text-danger fs-6" style="right:-10px;">*</span>
          </span>
          <select class="form-select w-100 fs-5 p-3 border border-primary rounded-4"
           name="" id="store">
            <option value="placeholder text">placeholder text</option>
          </select>
        </label>
        <!-- 姓名 -->
        <label for="name" class="form-label w-100 mt-2">
          <span class="position-relative">
            name
            <span class="position-absolute text-danger fs-6" style="right:-10px;">*</span>
          </span>
          <input type="text" class="form-control w-100 fs-5 p-3 border border-primary rounded-4"
           name="" id="name" placeholder="placeholder text">
        </label>
        <!-- 電話 -->
        <label for="phone" class="form-label w-100 mt-2">
          <span class="position-relative">
            phone
            <span class="position-absolute text-danger fs-6" style="right:-10px;">*</span>
          </span>
          <input type="tel" class="form-control w-100 fs-5 p-3 border border-primary rounded-4"
           name="" id="phone"
            placeholder="placeholder text">
        </label>
        <!-- 數量 -->
        <label for="amout" class="form-label w-100 mt-2">
          <span class="position-relative">
            Amout of consumption
            <span class="position-absolute text-danger fs-6" style="right:-10px;">*</span>
          </span>
          <input type="num" class="form-control w-100 fs-5 p-3 border border-primary rounded-4"
           name="" id="amout"
            placeholder="placeholder text">
        </label>
        <!-- 付款方式 -->
        <label for="payment" class="form-label w-100">
          <span class="position-relative">
            payment
            <span class="position-absolute text-danger fs-6" style="right:-10px;">*</span>
          </span>
          <select class="form-select w-100 fs-5 p-3 border border-primary rounded-4" name=""
           id="payment">
            <option value="placeholder text">placeholder text</option>
          </select>
        </label>
      </div>
      <!-- 提交按鈕 -->
      <div class="w-100 d-flex mt-3">
        <button type="button" class="btn btn-warning text-white fw-bold mt-3 mx-auto"
          style="width:200px; height: 57px; border-radius: 20px;">
          <span class="fs-4 ms-3" style=" letter-spacing: 10px;">submit</span>
        </button>
      </div>
    </form>
  </div>
</template>
