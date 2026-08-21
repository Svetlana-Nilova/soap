<script setup></script>

<template>
  <div class="flex about_content">
    <div class="img">
      <img src="../assets/catalog2.jpg" alt="картинка промо">
    </div>
    <div class="text">
      <h2>Варю с душой</h2>
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
  </div>
</template>

<style scoped>
.about_content {
  padding: 30px 30px;
  justify-content: space-evenly;

}

.text {
  max-width: 54%;
  padding-left: 30px;
}

.text>h2 {
  margin: 7px 0 26px 0;
}

.text>p {
  text-align: left;
  padding: 0 0 30px 5px;
}

.text_about {
  flex-wrap: wrap;
  gap: 20px;
}

.item {
  flex: 1;
  border: 3px solid #BC7B6F;
  border-radius: 30px;
  background-color: #F5F5F5;
  padding: 10px 12px;
  text-align: center;
}

.item h3 {
  font-family: 'Tenor Sans', sans-serif;
  font-size: 18px;
  letter-spacing: 10%;
  color: #BC7B6F;
  margin: 0 0 6px 0;
}

.item p {
  font-size: 16px;
  line-height: 20px;
  padding: 0 4px 10px;
  margin: 0;
}

.img {
  width: 80%;
  max-width: 538px;
  height: auto;
  background-color: #F5F5F5;
  border-radius: 60px;
}

.img img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  border: 3px solid #D9A69F;
  border-radius: 60px;
}

/* ===== Адаптив ===== */
@media (max-width: 1024px) {
  .about_content {
    flex-direction: column;
    align-items: center;
    padding: 30px 20px;
  }

  .img {
    display: none;
  }

  .text {
    /* font-size: 15px;
    line-height: 25px; */
    /* max-width: 0; */
    max-width: 100%;
    padding-left: 0;
  }

  .text>p {
    text-align: center;
    padding: 0 0 20px 0;
  }

  .text_about {
    flex-wrap: wrap;
    justify-content: center;
  }

  .item {
    flex: 1 1 200px;
    max-width: 300px;
  }
}

@media (max-width: 480px) {
  .about_content {
    padding: 20px 15px;
  }

  .img {
    width: 100%;
    border-radius: 40px;
  }

  .img img {
    border-radius: 40px;
  }

  .text>h2 {
    font-size: 24px;
    margin: 10px 0 16px;
  }

  .text>p {
    font-size: 16px;
    line-height: 26px;
  }

  .item {
    flex: 1 1 100%;
    max-width: 100%;
  }

  .item h3 {
    font-size: 16px;
  }

  .item p {
    font-size: 14px;
    line-height: 18px;
  }
}
</style>