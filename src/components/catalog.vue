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
    <div class="flex">
        <div class="container">
            <h2>
                Каталог
            </h2>
            <div class="slider-wrapper">
                <button class="btn left" @click="back">⬅</button>
                <div class="foto">
                    <div ref="slidesRef" class="slides flex">
                        <img src="../assets/catalog1.jpg" alt="">
                        <img src="../assets/catalog2.jpg" alt="">
                        <img src="../assets/catalog3.jpg" alt="">
                        <img src="../assets/catalog4.jpg" alt="">
                    </div>
                </div>
                <button class="btn right" @click="next">⮕</button>
            </div>
        </div>
        <div class="info">
            <h2>
                Как заказать?
            </h2>
            <div class="flex babl_item">
                <div class="babl">

                    <img src="../assets/babl.svg" alt="">
                    <p>1</p>
                </div>
                <p>Оставьте заявку</p>
            </div>
            <div class="flex babl_item">
                <div class="babl">

                    <img src="../assets/babl.svg" alt="">
                    <p>2</p>
                </div>
                <p>Мы свяжемся</p>
            </div>
            <div class="flex babl_item">
                <div class="babl">

                    <img src="../assets/babl.svg" alt="">
                    <p>3</p>
                </div>
                <p>Обсудим детали</p>
            </div>
            <div class="flex babl_item">
                <div class="babl">

                    <img src="../assets/babl.svg" alt="">
                    <p>4</p>
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

.btn {
    flex-shrink: 0;
    padding: 12px 18px;
    font-size: 24px;
    cursor: pointer;
    /* background: #eee;
  border: 1px solid #ccc;
  border-radius: 8px; */
}

.babl_item {
    align-items: center;
    justify-content: center;
}

.babl_item p {
    font-family: Tenor Sans;
    font-weight: 400;
    font-style: Regular;
    font-size: 28px;
    line-height: 50px;
    letter-spacing: 10%;
    text-align: center;
    vertical-align: middle;

}

.babl {
    width: 129px;
    height: 127px;
}

.foto {
    flex: 1;
    overflow: hidden;
    min-width: 0;
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
    border: 4px solid #d4b895;
    border-radius: 24px;
}

.info {
    width: 50%;
}
</style>