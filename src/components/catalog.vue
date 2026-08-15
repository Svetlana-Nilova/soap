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
            <h2>
                Каталог
            </h2>
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
            <h2>
                Как заказать?
            </h2>
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

.btn {
    flex-shrink: 0;
    padding: 18px 18px;
    font-size: 24px;
    cursor: pointer;
}

.left {
    background: url(../assets/left.svg) no-repeat center;
    border: 8px double #BC7B6F;
    border-radius: 8px;
}

.left:hover {
    border: 8px solid #BC7B6F;
}

.right {
    background: url(../assets/right.svg) no-repeat center;
    border: 8px double #BC7B6F;
    border-radius: 8px;
}

.right:hover {
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

/* КАК ЗАКАЗАТЬ */
.babl_item {
    align-items: center;
    margin: 0 15%;
}

.babl_item p {
    font-family: Tenor Sans;
    font-weight: 400;
    font-style: Regular;
    font-size: 28px;
    line-height: 50px;
    letter-spacing: 5%;
    vertical-align: middle;

    padding: 0 0 0 25px;
}

.babl {
    width: 129px;
    position: relative;
    display: inline-block;
}

.babl span {
    position: absolute;
    top: 42%;
    left: 50%;
    transform: translateX(-50%);

    font-family: Tenor Sans;
    font-weight: 400;
    font-style: Regular;
    font-size: 32px;
    line-height: 50px;
    letter-spacing: 10%;
    text-align: center;
    vertical-align: middle;
    color: #BC7B6F;


}

.babl img {
    width: 120px;
}

.babl span,
img {
    vertical-align: middle;
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