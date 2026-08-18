<script setup>

</script>

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
                <p>Оставьте телефон - наш мыловар свяжется с Вами и поможет с выбором. </p>

                <div class="inputs">
                    <input type="text" name="" id="" placeholder="Введите имя" required>
                    <input type="phone" name="" id="" placeholder="Введите телефон" required>
                    <textarea name="" id="" placeholder="Коментарий.." maxlength="260" required></textarea>
                </div>
                <input class="btn" type="submit" value="Отправить заявку">
            </form>
        </div>
    </div>

</template>

<style scoped>
.cont {
    padding: 50px 0;
}
.social {
    width: 45%;

    p {
        color: #BC7B6F;
    }
}

.btnS {
    font-family: 'Tenor Sans', sans-serif;
    background-color: #BC7B6F;
    color: #F5F5F5;
    font-family: Tenor Sans;
    font-weight: 400;
    font-style: Regular;
    font-size: 26px;
    letter-spacing: 10%;
    border-radius: 30px;
    padding: 12px 24%;
}

.a {
    margin-top: 15px;
    padding: 12px 106px;   
}


.vk,
.tg {
    position: relative;
    display: block;
    width: 100%;
}

.vk img,
.tg img {
    width: 60%;
    height: auto;
}

.tVk,
.tTg {
    position: absolute;
    top: 62%;
    left: 50%;
    transform: translate(-50%, -50%);
    text-align: center;
    color: #fff;

    p {
        font-family: Tenor Sans;
        font-weight: 400;
        font-style: Regular;
        font-size: 26px;
        leading-trim: NONE;
        line-height: 50px;
        letter-spacing: 10%;
        text-align: center;
        vertical-align: middle;

    }

}


.forma {
    width: 45%;
}

form {
    display: flex;
    flex-direction: column;
    flex-wrap: nowrap;
    justify-content: center;
    align-items: center;
    background: #f5f5f5;
    border: 3px solid #BC7B6F;
    border-radius: 25px;
    padding: 38px;
}

.inputs {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    border: 3px solid #BC7B6F;
    border-radius: 25px;
    padding: 12px 17px;

    input {
        font-family: 'Tenor Sans', sans-serif;
        border: 1px solid #BC7B6F;
        background: #f5f5f5;
        border-radius: 30px;
        padding: 5px 15px;
        color: #423A39;
        margin-bottom: 22px;

        width: 459px;
        height: 57px;
        border: 1px solid #D9A69F;
        border-radius: 30px;
    }

    textarea {
        font-family: 'Tenor Sans', sans-serif;
        border: 1px solid #BC7B6F;
        background: #f5f5f5;
        border-radius: 30px;
        padding: 5px 15px;
        color: #423A39;
        width: 459px;
        height: 57px;
        resize: none;
        overflow-y: none;

    }
}

input::placeholder {
    color: #423A39;
}

textarea::placeholder {
    padding: 4% 0px;
    color: #423A39;
}



.btn {
    font-family: 'Tenor Sans', sans-serif;
    width: 237px;
    height: 64px;
    font-weight: 400;
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
  border: 3px solid #BC7B6F;
  color: #F5F5F5;
}
</style>