<template>
  <!-- 區塊1(波浪線以上) -->
  <div class="bg-primary w-100 d-flex" style=" padding-bottom:150px;
    background-image:url('./images/bg-wave.png');
    background-position: 25% 75%;
    background-size: cover">
    <!-- 區塊1文字區域 -->
    <div class="text-center d-block pt-5 mx-auto" style="max-width:800px;">
      <!-- 大標題 -->
      <div style="letter-spacing: 5px;">
        <h1 class="text-white fw-bold">There is no one</h1>
        <h2 class="text-white fw-bold">who loves pain</h2>
      </div>
      <!-- 表單按鈕 -->
      <button id="form-header-button" type="button" @click="scrollToForm"
        class="btn btn-warning rounded-pill text-white fw-bold fs-4 mt-3 ps-4"
        style="width:200px; height: 57px; letter-spacing: 10px;">Form
      </button>
      <!-- 文章段落 -->
      <div class="container rounded rounded-5 mt-5 position-relative border border-3
           border-danger mx-auto" style="background-color:rgb(218, 228, 241, 1);">
        <!-- 第一段文字 -->
        <div class="py-3">
          <p>
            <img src="../assets/images/cactus.png" alt="">
            <span class="fw-bold fs-h4 text-primary">paragraph</span>
            <img src="../assets/images/cactus.png" alt="">
          </p>
          <p class="text-start ms-5">
            1. Lorem ipsum dolor sit amet, consectetur adipiscing elit.
          </p>
        </div>
        <!-- 第二段文字 -->
        <div class="py-3">
          <p>
            <img src="../assets/images/cactus.png" alt="">
            <span class="fw-bold fs-h4 text-primary">paragraph</span>
            <img src="../assets/images/cactus.png" alt="">
          </p>
          <p class="text-start ms-5">
            1. Quisque sodales leo
            <span class="text-decoration-underline">vitae vulputate auctor</span>.
          </p>
          <p class="text-start ms-5">
            2. Proin ac justo ut nisl tincidunt imperdiet.Maecenas
            viverra libero a pellentesque blandit.
          </p>
          <p class="text-start ms-5">
            3. Cras tristique tellus id leo bibendum, eu dapibus nisl accumsan.
          </p>
          <p class="text-start ms-5">
            4. Donec ultrices sapien <span class="fw-bold">vitae leo venenatis ullamcorper</span>.
          </p>
        </div>
        <!-- 文字區域旁圖案 -->
        <!-- 泡泡1 -->
        <div class="border rounded-circle position-absolute"
         style="width:20px; height:20px; z-index:1000;" id="bubble1">
        </div>
        <!-- 泡泡2 -->
        <div class="border rounded-circle position-absolute"
         style="width:12px; height:12px; z-index:1000;" id="bubble2">
        </div>
        <!-- 獨木舟1 -->
        <img src="../assets/images/sup1.png" class="position-absolute" alt=""
         style="z-index:1000; top:-50px; right:0">
        <!-- 獨木舟船槳 -->
        <img src="../assets/images/paddle.png" class="position-absolute" alt=""
         style="z-index:1000; top:-35px; right:0px"
          id="paddle">
        <!-- 獨木舟2 -->
        <img src="../assets/images/sup2.png" class="position-absolute" alt=""
          style="z-index:1000; bottom: -40px; left:50px">
        <!-- 煙火 -->
        <img src="../assets/images/fireworks.png" class="position-absolute" alt=""
          style="z-index:1000; bottom: -50px; left:30px" id="firework">
      </div>
    </div>
  </div>
  <!-- 波浪分隔線 -->
  <div class="w-100 overflow-hidden position-relative"
   style="height:109px; background-color:#e5e5e5">
    <img id="wave1" class="position-absolute"
     src="../assets/images/wave.png" alt="">
    <img id="wave2" class="position-absolute"
     src="../assets/images/wave.png" alt="">
  </div>
</template>

<style scoped>
/* 按鈕特效 */
@import '../assets/formbutton.scss';

/* 船槳擺動 */
#paddle {
  animation-name: paddle;
  animation-duration: 4s;
  animation-iteration-count: infinite;
  animation-timing-function: linear;
}

@keyframes paddle {
  0% {
    transform: rotate(0deg);
  }

  50% {
    transform: rotate(30deg);
  }

  100% {
    transform: rotate(0deg);
  }
}

/* 按鈕縮放 */
#form-header-button {
  animation-name: form-header-button;
  animation-duration: 4s;
  animation-iteration-count: infinite;
  animation-timing-function: ease-in-out;
}

@keyframes form-header-button {
  0% {
    transform: scale(1)
  }

  50% {
    transform: scale(1.2)
  }

  100% {
    transform: scale(1)
  }
}

/* 泡沫1浮動 */
#bubble1 {
  animation-name: bubble1;
  animation-duration: 2s;
  animation-iteration-count: infinite;
}

@keyframes bubble1 {
  0% {
    top: -50px;
    right: 30px;
    opacity: 1;
  }

  100% {
    top: -100px;
    right: 30px;
    opacity: 0;
  }
}

/* 泡沫2浮動 */
#bubble2 {
  animation-name: bubble2;
  animation-duration: 2s;
  animation-iteration-count: infinite;
}

@keyframes bubble2 {
  0% {
    top: -70px;
    right: 20px;
    opacity: 1;
  }

  100% {
    top: -120px;
    right: 20px;
    opacity: 0;
  }
}

/* 煙火特效 */
#firework {
  animation-name: firework;
  animation-duration: 4s;
  animation-iteration-count: infinite;
  animation-timing-function: ease-in;
}

@keyframes firework {
  0% {
    transform: scale(0);
    opacity: 1;
  }

  100% {
    transform: scale(2);
    opacity: 0;
  }
}

/* 波浪 */
#wave1 {
  top:-3px;
  animation-name:  wave-scroll-first;
  animation-timing-function: linear;
  animation-duration: 10s;
  animation-iteration-count: infinite;
}

@keyframes wave-scroll-first {
  0% {
    right:0;
  }

  100% {
    right:1564px;
  }
}

#wave2 {
  top:-3px;
  animation-name: wave-scroll-second;
  animation-timing-function: linear;
  animation-duration: 10s;
  animation-iteration-count: infinite;
}

@keyframes wave-scroll-second {
  0% {
    right:-1564px;
  }

  100% {
    right:0;
  }
}
</style>

<script>
export default {
  methods: {
    // 下滑至表單
    scrollToForm() {
      const formHeight = document.getElementById('form').clientHeight;
      window.scrollTo({
        top: formHeight + 270,
        behavior: 'smooth',
      });
    },
  },
};
</script>
