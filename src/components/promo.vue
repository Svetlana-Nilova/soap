<script setup></script>

<template>
  <div class="flex promo_content">
    <div class="backg">
      <div class="text">
        <h1 class="item">Мыло ручной работы, которое полюбит твоя кожа</h1>
        <p class="item">Каждый кусочек сварен вручную с любовью и внимание к деталям. Поможем подобрать идеальный
          кусочек
          под твой тип кожи.</p>
        <a class="item btn" href="../App.vue#Contacts">Отправить заявку</a>
      </div>
    </div>

    <div class="img">
      <img src="../assets/catalog3.jpg" alt="картинка промо">
    </div>
  </div>
</template>

<style scoped>
.promo_content {
  padding: 30px 90px;
  gap: 40px;
}

.backg {
  padding-right: 90px;
  display: flex;
}

.btn {
  font-family: 'Tenor Sans', sans-serif;
  display: inline-block;
  padding: 20px 50px;
  background-color: #F5F5F5;
  border: 3px solid #D9A69F;
  border-radius: 30px;
  color: #423A39;
}

.btn:hover {
  background-color: #BC7B6F;
  border-color: #BC7B6F;
  color: #F5F5F5;
}

.text {
  /* width: 55%; */
  display: flex;
  flex-direction: column;
  justify-content: space-evenly;
  align-items: center;
}

.text button {
  width: 287px;
  height: 90px;
  font-size: 18px;
}

.img {
  width: 538px;
  height: 538px;
  flex-shrink: 0;
  border-radius: 60px;
}

.img img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  border-radius: 60px;
  box-shadow: 0px 4px 4px 0px #00000080;
}

/* ===== Адаптив ===== */
@media (max-width: 1195px) {
  .promo_content {
    padding-right: 0px;
    padding: 30px 30px;
  }
  .img {
    width: 50%;
  }

}

@media (max-width: 1024px) {
  .promo_content {
    flex-direction: column;
    align-items: center;
    padding: 0px 0px;
  }

  .img {
    display: none;
  }

  .backg {
    padding-right: 0;
    background: url(../assets/catalog1.jpg) center;
    background-size: cover;
    border-radius: 30px;
  }


  .text {
    display: block;
    width: 100%;
    text-align: center;
    gap: 20px;
    border-radius: 30px;
    background-color: rgba(255, 255, 255, 0.749);
    margin: 3%;
    padding: 4%;
  }

  .text button {
    width: 80%;
    max-width: 287px;
    height: auto;
    padding: 18px 20px;
  }

  .img {
    width: 80%;
    max-width: 538px;
    height: auto;
    aspect-ratio: 1 / 1;
  }
}

@media (max-width: 480px) {

  .text h1 {
    font-size: 24px;
    line-height: 34px;
  }

  .text p {
    font-size: 16px;
    line-height: 26px;
  }

  .text button {
    font-size: 16px;
    padding: 14px 20px;
  }

  .img {
    width: 100%;
    border-radius: 40px;
  }

  .img img {
    border-radius: 40px;
  }
}
</style>