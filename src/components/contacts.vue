<script setup></script>

<template>
  <div class="flex cont">
    <div class="social">
      <div class="vk">
        <img src="../assets/vkC.svg" alt="">
        <div class="tVk">
          <p>Мы вконтакте</p>
          <button class="btnS a">vk.com</button>
        </div>
      </div>
      <div class="tg">
        <img src="../assets/tgC.svg" alt="">
        <div class="tTg">
          <p>Присоединяйтесь ко мне в Telegram</p>
          <button class="btnS">@username</button>
        </div>
      </div>
    </div>

    <div class="forma">
      <form action="#">
        <h2>Подберите идеальное мыло</h2>
        <p>Оставьте телефон - наш мыловар свяжется с Вами и поможет с выбором.</p>
        <div class="inputs">
          <input type="text" placeholder="Введите имя" required>
          <input type="phone" placeholder="Введите телефон" required>
          <textarea placeholder="Коментарий.." maxlength="260" required></textarea>
        </div>
        <input class="btn" type="submit" value="Отправить заявку">
      </form>
    </div>
  </div>
</template>

<style scoped>
.cont {
  padding: 50px 0;
  gap: 30px;
}

.social {
  width: 45%;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 30px;
}

.social p {
  color: #BC7B6F;
}

.btnS {
  font-family: 'Tenor Sans', sans-serif;
  background-color: #BC7B6F;
  color: #F5F5F5;
  font-size: 26px;
  letter-spacing: 10%;
  border-radius: 30px;
  padding: 12px 24%;
  border: none;
  cursor: pointer;
}

.a {
  margin-top: 15px;
  padding: 12px 106px;
}

.vk,
.tg {
  position: relative;
  width: 100%;
  max-width: 500px;
}

.vk img,
.tg img {
  width: 100%;
  height: auto;
  display: block;
}

.tVk,
.tTg {
  position: absolute;
  top: 62%;
  left: 50%;
  transform: translate(-50%, -50%);
  text-align: center;
  color: #fff;
  width: 80%;
}

.tVk p,
.tTg p {
  font-size: 26px;
  line-height: 50px;
  letter-spacing: 10%;
  margin: 0;
}

/* ФОРМА */
.forma {
  width: 53%;
  display: flex;
  justify-content: center;
}

form {
  display: flex;
  flex-direction: column;
  justify-content: space-around;
  align-items: center;
  background: #f5f5f5;
  border: 3px solid #BC7B6F;
  border-radius: 25px;
  padding: 38px 20px;
  width: 100%;
  max-width: 600px;
}

.inputs {
  display: flex;
  flex-direction: column;
  align-items: center;
  border: 3px solid #BC7B6F;
  border-radius: 25px;
  padding: 12px 17px;
  min-width: 100%;
}

.inputs input,
.inputs textarea {
  font-family: 'Tenor Sans', sans-serif;
  border: 1px solid #D9A69F;
  background: #f5f5f5;
  border-radius: 30px;
  padding: 5px 15px;
  color: #423A39;
  width: 100%;
  max-width: 459px;
  height: 57px;
  margin-bottom: 22px;
}

.inputs textarea {
  height: 57px;
  resize: none;
}

.inputs input::placeholder,
.inputs textarea::placeholder {
  color: #423A39;
}

.inputs textarea::placeholder {
  transform: translateY(100%);
}

.btn {
  font-family: 'Tenor Sans', sans-serif;
  width: 237px;
  height: 64px;
  font-size: 18px;
  padding: 7px 25px;
  background-color: #F5F5F5;
  border: 3px solid #D9A69F;
  border-radius: 30px;
  color: #423A39;
  cursor: pointer;
  margin-top: 25px;
}

.btn:hover {
  background-color: #BC7B6F;
  border-color: #BC7B6F;
  color: #F5F5F5;
}

/* ===== Адаптив ===== */
@media (max-width: 1024px) {
  .cont {
    align-items: center;
    padding: 30px 15px;
  }

  .social,
  .forma {
    width: 100%;
    max-width: 600px;
  }

  .social {
    width: 73%;
  }

  .vk,
  .tg {
    max-width: 100%;
  }

  .tVk,
  .tTg {
    top: 64%;
    display: flex;
    flex-direction: column;
  }

  .tVk p,
  .tTg p {
    font-size: 22px;
    line-height: 36px;
  }

  .btnS {
    font-size: 20px;
    padding: 10px 18%;
  }

  .a {
    padding: 10px 15%;
  }

  form {
    padding: 25px 15px;
  }

  .inputs input,
  .inputs textarea {
    max-width: 100%;
    height: 50px;
  }

  .inputs textarea {
    height: 50px;
  }

  .inputs textarea::placeholder {
    transform: translateY(70%);
  }
}

@media (max-width: 765px) {

  .tVk p,
  .tTg p {
    font-size: 18px;
    line-height: 26px;
  }
}

@media (max-width: 600px) {
  .cont {
    flex-direction: column-reverse;
  }

  .social {
    display: flex;
    flex-direction: row;
    width: auto;
  }

  .tVk p,
  .tTg p {
    font-size: 16px;
    line-height: 26px;
  }

  .btnS {
    font-size: 16px;
    padding: 8px 12%;
  }

  .a {
    padding: 8px 10%;
  }

  form h2 {
    font-size: 24px;
  }

  form p {
    font-size: 16px;
  }

  .inputs input,
  .inputs textarea {
    height: 44px;
    font-size: 14px;
  }

  .inputs textarea::placeholder {
    transform: translateY(50%);
  }

  .btn {
    width: 100%;
    max-width: 237px;
    height: 54px;
    font-size: 16px;
  }
}

@media (max-width: 480px) {
  .social {
    gap: 20px;
  }

  .vk img,
  .tg img {
    border-radius: 20px;
  }

  .tVk,
  .tTg {
    top: 66%;
    width: 90%;
  }

  .tVk p,
  .tTg p {
    font-size: 10px;
    line-height: 14px;
  }

  .tTg p {
    margin-top: -7px;
    margin-bottom: 7px;
  }

  .btnS {
    font-size: 12px;
    padding: 0px 10%;
    border-radius: 20px;
  }

  form {
    padding: 20px 10px;
    border-radius: 20px;
  }

  .inputs {
    padding: 10px 12px;
    border-radius: 20px;
  }

  .inputs input,
  .inputs textarea {
    height: 40px;
    font-size: 13px;
    margin-bottom: 15px;
    border-radius: 20px;
  }

  .inputs textarea::placeholder {
    transform: translateY(30%);
  }

  .btn {
    height: 48px;
    font-size: 14px;
    margin-top: 18px;
  }
}
@media (max-width: 480px) {
  .tTg p {
    margin-top: -2px;
    margin-bottom: 2px;
  }
}
</style>