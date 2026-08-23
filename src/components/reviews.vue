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
  gap: 15px;
}

.revCont {
  width: 1126px;
  max-width: 100%;
  height: 517px;
  border-radius: 30px;
  border: 3px solid #BC7B6F;
  background: #F5F5F5;
  overflow: hidden;
  flex-shrink: 1;
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
  padding: 20px;
  gap: 20px;
}

.review img {
  width: 462px;
  max-width: 50%;
  height: 420px;
  object-fit: cover;
  border-radius: 30px;
  box-shadow: 0px 4px 4px 0px #00000080;
}

.btn {
  flex-shrink: 0;
  padding: 18px 18px;
  font-size: 24px;
  cursor: pointer;
  background: transparent;
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

.text {
  text-align: left;
}

.text p:first-child {
  font-weight: bold;
  font-size: 22px;
  color: #BC7B6F;
}

.stars {
  width: 209px;
  height: 41px;
  background: url(../assets/stars5.svg) no-repeat;
  background-size: contain;
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

/* ===== Адаптив ===== */
@media (max-width: 1024px) {
  .revCont {
    height: auto;
    border-radius: 20px;
  }

  .review {
    padding: 20px;
    height: 100%;
    justify-content: center;
  }

  .review img {
    width: 80%;
    max-width: 300px;
    height: auto;
    aspect-ratio: 1 / 1;
  }

  .text {
    text-align: center;
  }

  .btn {
    padding: 12px 12px;
    border-width: 5px;
    background-size: 60% 60%;
    min-width: 40px;
    min-height: 40px;
  }
}

@media (max-width: 600px) {
  .conteiner {
    gap: 8px;
  }

  .revCont {
    border-radius: 16px;
  }

  .review img {
    max-width: 200px;
  }

  .text p:first-child {
    font-size: 18px;
  }
  .stars {
    width: 130px;
    height: 26px;
  }
  .text p:last-child {
    font-size: 14px;
  }

  .dots {
    gap: 8px;
  }
  .dot {
    width: 10px;
    height: 10px;
  }
}

/* ===== Мобильная версия (≤480px): картинка слева, текст справа, кнопки под блоком ===== */
@media (max-width: 480px) {
  .conteiner {
    flex-wrap: wrap;
    justify-content: center;
    gap: 10px;
  }

  .revCont {
    order: 0;
    width: 100%;
    min-height: auto;
    height: auto;
    border-radius: 16px;
  }

  .slides {
    height: auto;
  }

  .review {
    flex-direction: row !important;
    align-items: center;
    padding: 15px;
    gap: 15px;
    justify-content: flex-start;
    height: auto;
  }

  .review img {
    width: 100px;
    max-width: 100px;
    height: 100px;
    flex-shrink: 0;
    aspect-ratio: 1 / 1;
    border-radius: 16px;
  }

  .text {
    text-align: left;
    flex: 1;
  }

  .text p:first-child {
    font-size: 16px;
    margin-bottom: 4px;
  }
  .stars {
    width: 100px;
    height: 20px;
  }
  .text p:last-child {
    font-size: 14px;
    line-height: 1.4;
  }

  /* Кнопки (стрелки) под блоком, на одной линии */
  .btn {
    order: 1;
    flex: 0 0 auto;
    padding: 8px 8px;
    min-width: 36px;
    min-height: 36px;
    border-width: 4px;
    background-size: 50% 50%;
    margin: 0 5px;
  }

  .dots {
    display: none; /* можно оставить, если нужно – убери эту строку */
  }
}
</style>