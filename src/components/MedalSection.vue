<template>
  <div class="py-5 d-flex flex-column" style="background-color: #e5e5e5;
  background-image: url('./images/sandbg.png');">
    <div class="container" style="max-width:700px;">
      <div class="row gy-5 row-cols-2 row-cols-md-3">
        <!-- 金牌 -->
        <div class="col" v-for="(item, order) in goldMedalData" :key="order">
          <div class="bg-white rounded-4 text-center position-relative mx-auto"
           style="width:178px; height: 112px;">
            <img class="position-absolute start-50 translate-middle" style="top:15px"
              src="../assets/images/gold-medal.png" alt="">
            <span class="position-absolute start-50 translate-middle text-white
              fw-bold rounded rounded-5" style="top:10px;">{{ item.alphabet }}</span>
            <span class="position-absolute px-2 fw-bold fs-6 rounded rounded-5"
             style="color:#B3B960; right:10px; top:20px; border:solid 1px #B3B960">
             {{ item.num }}
            </span>
            <p class="fs-4 fw-bold" style="color: #B3B960; padding-top: 65px;">
              {{ item.text }}
            </p>
          </div>
        </div>
        <!-- 銀牌 -->
        <div class="col" v-for="(item, order) in silverMedalData" :key="order">
          <div class="bg-white rounded-4 text-center position-relative mx-auto"
           style="width:178px; height: 112px;">
            <img class="position-absolute start-50 translate-middle" style="top:10px"
              src="../assets/images/gray-medal.png" alt="">
            <span class="position-absolute start-50 translate-middle text-white
            fw-bold rounded rounded-5" style="top:10px;">{{ item.alphabet }}</span>
            <span class="position-absolute px-2 fw-bold fs-6 rounded rounded-5"
             style="color:#A0BCC8; right:10px; top:20px; border:solid 1px #A0BCC8">
             {{ item.num }}
            </span>
            <p class="fs-4 fw-bold" style="color: #A0BCC8; padding-top: 60px;">
              {{ item.text }}
            </p>
          </div>
        </div>
      </div>
    </div>
  </div>
  <div class="py-5 d-flex flex-column" style="background-color: #e5e5e5;">
    <!-- 燈塔及文字 -->
    <div class="text-center pt-5 pb-2 d-inline-block position-relative mx-auto"
     style="width: 200px;">
      <p class="text-danger fw-bold">13.32</p>
      <p class="fw-bold">who seeks after it and</p>
      <p class="fw-bold">wants to have it</p>
      <!-- 斜線 -->
      <div class="bg-primary position-absolute"
        style="width:90px; height:1px; transform:rotate(80deg); top:100px; left:-60px;"></div>
      <div class="bg-primary position-absolute"
        style="width:90px; height:1px; transform:rotate(-80deg); top:100px; right:-60px;"></div>
    </div>
    <img class="mx-auto" src="../assets/images/lighthouse.png" alt=""
     style="width:56.03px; height:164px">
  </div>
</template>

<script>
export default {
  data() {
    return {
      goldMedalData: [
        {
          alphabet: 'A',
          num: 'ONE',
          text: 'dehumidifier',
        },
        {
          alphabet: 'B',
          num: 'ONE',
          text: 'range hood',
        },
        {
          alphabet: 'C',
          num: 'ONE',
          text: 'vacuum cleaner',
        },
      ],
      silverMedalData: [
        {
          alphabet: 'C',
          num: 'ONE',
          text: 'dehumidifier',
        },
        {
          alphabet: 'D',
          num: 'ONE',
          text: 'dehumidifier',
        },
        {
          alphabet: 'E',
          num: 'ONE',
          text: 'dehumidifier',
        },
        {
          alphabet: 'F',
          num: 'ONE',
          text: 'dehumidifier',
        },
        {
          alphabet: 'G',
          num: 'FIVE',
          text: 'dehumidifier',
        },
        {
          alphabet: 'H',
          num: 'TEN',
          text: 'dehumidifier',
        },
      ],
    };
  },
};
</script>
