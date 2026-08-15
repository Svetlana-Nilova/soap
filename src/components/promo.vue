<script setup>

</script>

<template>
    <div class="flex promo_content">
        <div class="text">
            <h1 class="item">Мыло ручной работы, которое полюбит твоя кожа</h1>
            <p class="item">Каждый кусочек сварен вручную с любовью и внимание к деталям. Поможем подобрать идеальный
                кусочек под твой тип кожи.</p>
            <button class="item">Отправить заявку</button>
        </div>
        <div class="img">
            <img src="../assets/catalog3.jpg" alt="картинка промо">
        </div>
    </div>
</template>

<style scoped>
/* .flex>div {
    width: 55%;
} */

.promo_content {
    padding: 30px 90px 30px 90px;
}

.text {
    width: 55%;
    padding: 0 90px 0 0;
    display: flex;
    flex-direction: column;
    flex-wrap: nowrap;
    justify-content: space-evenly;
    align-items: center;

    button {
        width: 287px;
        height: 90px;
        font-family: 'Tenor Sans', sans-serif;
        font-weight: 400;
        font-size: 18px;
    }
}

.img {
    width: 538px;
    height: 538px;
    background-color: #F5F5F5;
    border-radius: 60px;

    img {
        width: 100%;
        height: 100%;
        object-fit: cover;
        border: 3px solid #D9A69F;
        border-radius: 60px;
    }
}
</style>