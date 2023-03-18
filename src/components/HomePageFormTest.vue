<template>
    <!-- 表單區域 -->
    <div style="background-color:#E5E5E5; padding:100px 0 30px 0;">
        <form action="" class="container position-relative d-flex flex-column" id="form">
            <!-- 標題 -->
            <div class="rounded-5 border border-2 border-danger rounded-4 bg-white
             py-2 ps-4 pe-3 d-inline position-absolute start-50 translate-middle-x
              fw-bold text-danger" style="letter-spacing: 10px; top:-20px;">
                FORM
                <img src="../assets/images/turtle.png" class="position-absolute" alt=""
                    style="z-index:1000; top:-20px; right:-40px">
            </div>
            <!-- 資料填寫區 -->
            <div class="bg-white border border-danger border-2 rounded pt-5 pb-3 px-3 mx-auto"
             style="max-width:800px;">
                <!-- 商店 -->
                <label for="store" class="form-label w-100 position-relative">
                    <span class="position-relative">
                        store
                        <span class="position-absolute text-danger fs-6"
                         style="right:-10px;">*</span>
                    </span>
                    <input type="text"  name="store" id="store" placeholder="placeholder text"
                     class="form-control shadow-none w-100 fs-5 p-3 rounded-4"
                       @focus="storeExtended" @blur="storeInvisible" v-model="answerStore"
                       autocomplete="off"  v-if="!errorMessage.store">
                    <input type="text"  name="store" id="store" placeholder="placeholder text"
                     class="form-control shadow-none w-100 fs-5 p-3 rounded-4 border-danger"
                       @focus="storeExtended" @blur="storeInvisible"  v-model="answerStore"
                       autocomplete="off"  v-if="errorMessage.store">
                    <img src="../assets/images/caret-down-fill.svg" alt=""
                    class="position-absolute" style="right:15px; top:45px">
                    <div v-if="storeOption.extended" class="position-absolute w-100"
                     style="end:0; start:0; z-index: 10000;
                     background-color: white; border:solid black 1px;">
                     <p v-for="(item) in storeOption.options" :key="item"
                      class="px-3 mb-0 option"
                      @mousedown="chooseStore(item)" @keypress="enter">
                      {{item}}
                     </p>
                    </div>
                    <p v-if="errorMessage.store" class="fs-5">{{ errorMessage.store[0] }}</p>
                </label>
                <!-- 姓名 -->
                <label for="name" class="form-label w-100 mt-2">
                    <span class="position-relative">
                        name
                        <span class="position-absolute text-danger fs-6"
                         style="right:-10px;">*</span>
                    </span>
                    <input type="text"  name="name" id="name" placeholder="placeholder text"
                     class="form-control shadow-none w-100 fs-5 p-3 rounded-4"
                     v-if="!errorMessage.name" v-model="answerName">
                    <input type="text"  name="name" id="name" placeholder="placeholder text"
                     class="form-control shadow-none w-100 fs-5 p-3 rounded-4 border-danger"
                     v-if="errorMessage.name" v-model="answerName">
                    <p v-if="errorMessage.name" class="fs-5">{{ errorMessage.name[0] }}</p>
                </label>
                <!-- 電話 -->
                <label for="phone" class="form-label w-100 mt-2">
                    <span class="position-relative">
                        phone
                        <span class="position-absolute text-danger fs-6"
                         style="right:-10px;">*</span>
                    </span>
                    <input type="number" name="phone" id="phone"
                     placeholder="placeholder text" v-model="answerPhone" v-if="!errorMessage.phone"
                    class="form-control shadow-none w-100 fs-5 p-3 rounded-4">
                    <input type="number" name="phone" id="phone"
                     placeholder="placeholder text" v-model="answerPhone" v-if="errorMessage.phone"
                    class="form-control shadow-none w-100 fs-5 p-3 rounded-4 border-danger">
                    <p v-if="errorMessage.phone" class="fs-5">{{ errorMessage.phone[0] }}</p>
                </label>
                <!-- 數量 -->
                <label for="amout" class="form-label w-100 mt-2">
                    <span class="position-relative">
                        Amout of consumption
                        <span class="position-absolute text-danger fs-6"
                         style="right:-10px;">*</span>
                    </span>
                    <input type="number" name="amout" id="amout" placeholder="placeholder text"
                    class="form-control shadow-none w-100 fs-5 p-3 rounded-4"
                     v-model="answerAmout" v-if="!errorMessage.amout">
                    <input type="number" name="amout" id="amout" placeholder="placeholder text"
                    class="form-control shadow-none w-100 fs-5 p-3 rounded-4 border-danger"
                     v-model="answerAmout" v-if="errorMessage.amout">
                    <p v-if="errorMessage.amout" class="fs-5">{{ errorMessage.amout[0] }}</p>
                </label>
                <!-- 付款方式 -->
                <label for="payment" class="form-label w-100">
                    <span class="position-relative">
                        payment
                        <span class="position-absolute text-danger fs-6"
                         style="right:-10px;">*</span>
                    </span>
                    <select name="payment" id="payment"
                    class="form-select shadow-none w-100 fs-5 p-3 rounded-4"
                    v-model="answerPayment" v-if="!errorMessage.payment">
                        <option value="placeholder text" selected disabled>
                          placeholder text
                        </option>
                        <option value="digital payment">digital payment</option>
                        <option value="ATM">ATM</option>
                    </select>
                    <select name="payment" id=""
                    class="form-select shadow-npaymentone w-100 fs-5 p-3 rounded-4 border-danger"
                    v-model="answerPayment" v-if="errorMessage.payment">
                        <option value="placeholder text" selected disabled>
                          placeholder text
                        </option>
                        <option class="option" value="digital payment">digital payment</option>
                        <option class="option" value="ATM">ATM</option>
                    </select>
                    <p v-if="errorMessage.payment" class="fs-5">{{ errorMessage.payment[0] }}</p>
                </label>
            </div>
            <!-- 提交按鈕 -->
            <div class="w-100 d-flex mt-3" v-if="validatedOrNot === 'notValidated'">
                <button type="button" @click="validate"
                 class="btn btn-warning text-white fw-bold mt-3 mx-auto"
                 style="width:200px; height: 57px; border-radius: 50px;">
                    <span class="fs-4 ms-3" style=" letter-spacing: 10px;">submit</span>
                </button>
            </div>
            <div class="w-100 d-flex mt-3" v-if="validatedOrNot === 'passed'">
                <button type="button" @click="validate"
                 class="btn btn-warning text-white fw-bold mt-3 mx-auto"
                 style="width:230px; height: 57px; border-radius: 50px;">
                    <img src="../assets/images/success-icon.png" alt="">
                    <span class="fs-4 ms-3"
                     style="color:#E6FFB1; letter-spacing: 10px;">success</span>
                </button>
            </div>
            <div class="w-100 d-flex flex-column mt-3" v-if="validatedOrNot === 'failed'">
                <button type="button" @click="validate"
                 class="btn btn-warning text-white fw-bold mt-3 mx-auto"
                 style="width:230px; height: 57px; border-radius: 50px;">
                    <img src="../assets/images/failure-icon.png" alt="">
                    <span class="fs-4 ms-3"
                     style="color:#FFE3E3; letter-spacing: 10px;">failure</span>
                </button>
            </div>
        </form>
    </div>
</template>

<style>
.border-focus{
  border-color: #93BBF9;
}

.option:hover{
  background-color: #03a2e6;
  color: white;
}

</style>

<script>
import validate from 'validate.js';

export default {
  data() {
    return {
      answerStore: '',
      answerName: '',
      answerPhone: '',
      answerAmout: '',
      answerPayment: 'placeholder text',
      validatedOrNot: 'notValidated',
      errorMessage: {},
      storeSearchKeyWord: '',
      storeDefaultOptions: [
        'store1',
        'store2',
        'store3',
        'store4',
        'store5',
        'store6',
        'store7',
        'store8',
        'store9',
        'store10',
      ],
      storeOption: {
        extended: false,
        options: [
          'store1',
          'store2',
          'store3',
          'store4',
          'store5',
          'store6',
          'store7',
          'store8',
          'store9',
          'store10',
        ],
      },
    };
  },
  methods: {
    chooseStore(storeName) {
      console.log('chooseStore', storeName);
      this.answerStore = storeName;
    },
    storeExtended() {
      this.storeOption.extended = true;
    },
    storeInvisible() {
      this.storeOption.extended = false;
    },
    validate() {
      validate.validators.presence.options = { message: '為必填項目' };
      const constraints = {
        store: {
          presence: true,
        },
        name: {
          presence: true,
          format: {
            pattern: /^[\u4e00-\u9fa5_a-za-z]+$/,
            message: '姓名僅限輸入中文及英文',
          },
        },
        phone: {
          presence: true,
          numericality: {
            onlyInteger: true,
            greaterThan: 899999999,
            lessThanOrEqualTo: 999999999,
            message: '格式錯誤',
          },
        },
        amout: {
          presence: true,
          numericality: {
            onlyInteger: true,
            greaterThan: 0,
            message: '數量須大於 0',
          },
        },
        payment: {
          exclusion: {
            within: ['placeholder text'],
            message: '為必填項目',
          },
        },
      };

      //  驗證
      const form = document.getElementById('form');
      const error = validate(form, constraints);
      console.log(error);
      if (error === undefined) {
        console.log('success');
        this.validatedOrNot = 'passed';
        this.errorMessage = {};
      } else {
        console.log('fail');
        this.validatedOrNot = 'failed';
        this.errorMessage = error;
      }
    },
  },
  watch: {
    answerStore() {
      if (this.answerStore === '') {
        this.storeOption.options = this.storeDefaultOptions;
      } else {
        this.storeOption.options = [];
        this.storeDefaultOptions.forEach((item) => {
          const matchResult = item.match(this.answerStore);
          if (matchResult !== null) {
            this.storeOption.options.push(item);
          }
        });
      }
    },
  },
};
</script>
