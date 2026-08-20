<script setup></script>

<template>
  <div class="flex promo_content">
    <div class="text">
      <h1 class="item">Мыло ручной работы, которое полюбит твоя кожа</h1>
      <p class="item">Каждый кусочек сварен вручную с любовью и внимание к деталям. Поможем подобрать идеальный кусочек под твой тип кожи.</p>
      <button class="item">Отправить заявку</button>
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

.text {
  width: 55%;
  padding-right: 90px;
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
  .promo_content {
    flex-direction: column;
    align-items: center;
    padding: 30px 20px;
  }

  .text {
    width: 100%;
    padding-right: 0;
    text-align: center;
    gap: 20px;
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
  .promo_content {
    padding: 20px 15px;
  }

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