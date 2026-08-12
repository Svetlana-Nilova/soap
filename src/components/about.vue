<script setup>
import { ref } from 'vue'

</script>

<template>
    <div class="flex promo_content">
        <div class="img">
            <img src="" alt="картинка промо">
        </div>
        <div class="text">
            <h2>
                Варю с душой
            </h2>
            <p>
                Привет! Я Катя, мыловар с 5-летним стажем. Каждый кусок я создаю вручную по авторским рецептам,
                использую только натуральные масла, травяные отвары и эфирные масла высшего качества.
                Моё мыло не сушит кожу, не вызывает аллергии и превращает каждое мытьё в маленький ритуал заботы о себе.
            </p>
            <div class="flex text_about">
                <div class="item">
                    <h3>100% Натурально</h3>
                    <p>Только масла холодного отжима и травяные экстракты</p>
                </div>
                <div class="item">
                    <h3>Ручная работа</h3>
                    <p>Каждый кусок уникален - варю с душой и вниманием</p>
                </div>
                <div class="item">
                    <h3>Без химии</h3>
                    <p>Никаких сульфатов, парабенов и синтетических отдушек</p>
                </div>
            </div>

        </div>
        <!-- <div class="img">
            <img src="" alt="картинка промо">
        </div> -->
    </div>

</template>

<style scoped>
/* .flex {
    display: flex;
} */

.promo_content {
    padding: 30px 90px 30px 90px;
}


.text {
    width: 59%;
    padding: 0 0px 0 30px;
    /* display: flex;
    flex-direction: column;
    flex-wrap: nowrap;
    justify-content: space-around;
    align-items: center; */

}

.text>h2 {
    margin: 7px 0 26.650px 0;

}

.text>p {
    text-align: left;
    padding: 0 0 30px 5px;
}


.item {
    width: 33%;
    border: 3px solid #BC7B6F;
    border-radius: 30px;
    background-color: #F5F5F5;
    padding: 5px;

    h3 {
        font-family: Tenor Sans;
        font-size: 18px;
        letter-spacing: 10%;
        color: #BC7B6F;

    }

    p {
        font-family: Tenor Sans;
        font-weight: 400;
        font-style: Regular;
        font-size: 16px;
        line-height: 20px;
        padding: 0 4px 10px;

    }
}

.item:first-child {
    margin-right: 20px;
}

.item:last-child {
    margin-left: 20px;
}

.img {
    width: 538px;
    height: 538px;
    background-color: #F5F5F5;
    border: 3px solid #D9A69F;
    border-radius: 60px;
}
</style>
