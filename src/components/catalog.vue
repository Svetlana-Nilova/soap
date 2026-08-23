<script setup>
import { ref, onMounted, computed } from 'vue'

const cSlide = ref(0)
const slidesRef = ref(null)
const slidesC = ref(0)

const pos = computed(() => `${cSlide.value * -100}%`)

onMounted(() => {
  if (slidesRef.value) {
    slidesC.value = slidesRef.value.childElementCount
  }
})

function next() {
  if (cSlide.value >= slidesC.value - 1) cSlide.value = 0
  else cSlide.value++
}

function back() {
  if (cSlide.value <= 0) cSlide.value = slidesC.value - 1
  else cSlide.value--
}
</script>

<template>
  <div class="flex grechnevai">
    <div class="container">
      <h2>Каталог</h2>
      <div class="slider-wrapper">
        <button class="btn left" @click="back"></button>
        <div class="foto">
          <div ref="slidesRef" class="slides flex">
            <img src="../assets/catalog1.jpg" alt="">
            <img src="../assets/catalog2.jpg" alt="">
            <img src="../assets/catalog3.jpg" alt="">
            <img src="../assets/catalog4.jpg" alt="">
          </div>
        </div>
        <button class="btn right" @click="next"></button>
      </div>
      <div class="dots">
        <span v-for="n in slidesC" :key="n - 1" class="dot" :class="{ active: cSlide === n - 1 }"
          @click="cSlide = n - 1"></span>
      </div>
    </div>

    <div class="info">
      <h2>Как заказать?</h2>
      <div class="flex babl_item">
        <div class="babl">
          <img src="../assets/babl.svg" alt="">
          <span>1</span>
        </div>
        <p>Оставьте заявку</p>
      </div>
      <div class="flex babl_item">
        <div class="babl">
          <img src="../assets/babl.svg" alt="">
          <span>2</span>
        </div>
        <p>Мы свяжемся</p>
      </div>
      <div class="flex babl_item">
        <div class="babl">
          <img src="../assets/babl.svg" alt="">
          <span>3</span>
        </div>
        <p>Обсудим детали</p>
      </div>
      <div class="flex babl_item">
        <div class="babl">
          <img src="../assets/babl.svg" alt="">
          <span>4</span>
        </div>
        <p>Получите мыло</p>
      </div>
    </div>
  </div>
</template>

<style scoped>
* {
  box-sizing: border-box;
}

.grechnevai {
  padding: 0 0 30px 0;
  gap: 20px;
}

/* КАТАЛОГ */
.container {
  width: 50%;
  padding: 0 20px 20px 20px;
}

.slider-wrapper {
  display: flex;
  align-items: center;
  gap: 10px;
  width: 100%;
}

.slides {
  display: flex;
  flex-wrap: nowrap;
  width: 100%;
  transition: transform 1s;
  transform: translateX(v-bind(pos));
}

.slides img {
  width: 100%;
  flex-shrink: 0;
  height: 420px;
  display: block;
  object-fit: cover;
  border-radius: 24px;
}

.btn {
  flex-shrink: 0;
  padding: 18px 18px;
  font-size: 24px;
  cursor: pointer;
  background-color: transparent;
  border: none;
}

.left {
  background: url(../assets/left_off.svg) no-repeat center;
  border: 8px double #BC7B6F;
  border-radius: 8px;
}

.left:hover {
  background: url(../assets/left_on.svg) no-repeat center;
  border: 8px solid #BC7B6F;
}

.right {
  background: url(../assets/right_off.svg) no-repeat center;
  border: 8px double #BC7B6F;
  border-radius: 8px;
}

.right:hover {
  background: url(../assets/right_on.svg) no-repeat center;
  border: 8px solid #BC7B6F;
}

.dots {
  display: flex;
  justify-content: center;
  gap: 12px;
  margin-top: 20px;
}

.dot {
  width: 14px;
  height: 14px;
  border-radius: 50%;
  background: #F5F5F5B2;
  cursor: pointer;
  transition: background 0.3s, transform 0.2s;
}

.dot.active {
  background: #BC7B6F;
  transform: scale(1.2);
}

.dot:hover {
  background: #BC7B6F;
}

.foto {
  flex: 1;
  overflow: hidden;
  min-width: 0;
  box-shadow: 0px 4px 4px 0px #00000080;
  border-radius: 30px;
}

/* КАК ЗАКАЗАТЬ */
.info {
  width: 50%;
}

.babl_item {
  align-items: center;
  margin: 0 15%;
  gap: 10px;
}

.babl_item p {
  font-size: 28px;
  line-height: 50px;
  letter-spacing: 5%;
  padding-left: 25px;
  margin: 0;
}

.babl {
  width: 129px;
  position: relative;
  display: inline-block;
  flex-shrink: 0;
}

.babl span {
  position: absolute;
  top: 42%;
  left: 46%;
  transform: translateX(-50%);
  font-size: 32px;
  line-height: 50px;
  letter-spacing: 10%;
  color: #BC7B6F;
}

.babl img {
  width: 120px;
  display: block;
}

/* ===== Адаптив ===== */
@media (max-width: 1024px) {
  .grechnevai {
    flex-direction: column;
    align-items: center;
    padding: 0 10px 30px;
  }

  .container,
  .info {
    width: 100%;
    max-width: 700px;
  }

  .container {
    max-width: 100%;
    padding: 0 10px 20px;
  }

  .babl_item {
    margin: 0 20%;
  }

  .babl_item p {
    font-size: 24px;
    line-height: 40px;
    padding-left: 15px;
  }

  .slides img {
    height: 550px;
  }
}

@media (max-width: 600px) {
  .slider-wrapper {
    gap: 6px;
  }

  .btn {
    padding: 10px 10px;
    border-width: 5px;
    background-size: 60% 60%;
    min-width: 40px;
    min-height: 40px;
  }

  .slides img {
    height: 400px;
    border-width: 3px;
    border-radius: 16px;
  }

  .babl {
    width: 80px;
  }

  .babl img {
    width: 70px;
  }

  .babl span {
    left: 44%;
    font-size: 22px;
    line-height: 30px;
  }

  .babl_item p {
    font-size: 18px;
    line-height: 28px;
    padding-left: 10px;
  }

  .dots {
    gap: 8px;
    margin-top: 12px;
  }

  .dot {
    width: 10px;
    height: 10px;
  }
}

@media (max-width: 480px) {
  .slider-wrapper {
    flex-wrap: wrap;
    justify-content: center;
    gap: 10px;
  }

  .foto {
    flex: 0 0 100%;
    max-width: 100%;
  }

  .slider-wrapper .btn {
    order: 1;
    margin: 5px 0;
  }

  .dots {
    display: none;
  }

  .btn {
    flex: 0 0 auto;
    margin: 0 5px;
  }

  .slides img {
    height: 300px;
  }

  .babl_item {
    margin: 0 6%;
  }

  .babl_item p {
    padding-left: 0;
  }

  .info h2 {
    font-size: 24px;
  }
}
</style>