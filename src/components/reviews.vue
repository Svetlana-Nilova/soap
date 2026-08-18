<script setup>
import { ref, onMounted, computed } from 'vue'

const cSlide = ref(0)
const slidesRef = ref(null)
const slidesC = ref(0)

const pos = computed(() => `${cSlide.value * -100 / slidesC.value}%`)
const slidesWidth = computed(() => `${slidesC.value * 100}%`)
const slideFlex = computed(() => `0 0 ${100 / slidesC.value}%`)

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
  <h2>Отзывы</h2>
  <div class="flex conteiner">
    <button class="btn left" @click="back"></button>
    <div class="revCont">
      <div ref="slidesRef" class="slides flex" :style="{ width: slidesWidth }">
        <div class="flex review" :style="{ flex: slideFlex }">
          <img src="../assets/catalog2.jpg" alt="">
          <div class="text">
            <p>Валерия</p>
            <div class="stars"></div>
            <p>Очень классной мыло! Рекомендую всем)</p>
          </div>
        </div>
        <div class="flex review" :style="{ flex: slideFlex }">
          <img src="../assets/catalog1.jpg" alt="">
          <div class="text">
            <p>Валерия</p>
            <div class="stars"></div>
            <p>Очень классной мыло! Рекомендую всем)</p>
          </div>
        </div>
      </div>
    </div>
    <button class="btn right" @click="next"></button>
  </div>
  <div class="dots">
    <span v-for="n in slidesC" :key="n - 1" class="dot" :class="{ active: cSlide === n - 1 }"
      @click="cSlide = n - 1"></span>
  </div>
</template>

<style scoped>
.conteiner {
  justify-content: center;
  align-items: center;
}

.revCont {
  width: 1126px;
  height: 517px;
  border-radius: 30px;
  border: 3px solid #BC7B6F;
  background: #F5F5F5;
  margin: 0 30px;
  overflow: hidden;
}

.slides {
  display: flex;
  flex-wrap: nowrap;
  transition: transform 1s;
  transform: translateX(v-bind(pos));
  height: 100%;
}

.review {
  align-items: center;
  justify-content: space-evenly;
}

.review img {
  width: 462px;
  height: 420px;
  border-radius: 30px;
}

.btn {
  flex-shrink: 0;
  padding: 18px 18px;
  font-size: 24px;
  cursor: pointer;
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

.text {
  text-align: left !important;
}

.dots {
  display: flex;
  justify-content: center;
  gap: 12px;
  margin-top: 20px;
  margin-bottom: 20px;
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

.stars {
  width: 209px;
  height: 41px;
  background: url(../assets/stars5.svg) no-repeat;
}
</style>