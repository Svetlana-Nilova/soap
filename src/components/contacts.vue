<script setup>

</script>

<template>

    <div class="flex">
        <div class="social"></div>
        <div class="forma">
            <form action="#">
                <h2>Подберите идеальное мыло</h2>
                <p>Оставьте телефон - наш мыловар свяжется с Вами и поможет с выбором. </p>

                <div class="inputs">
                    <input type="text" name="" id="" required> <br>
                    <input type="phone" name="" id="" required><br>
                    <textarea name="" id="" required></textarea><br>
                </div>
                <input class="btn" type="submit" value="Отправить заявку">
            </form>
        </div>
    </div>

</template>

<style scoped>

form {
    background: #f5f5f5;
    border: 3px solid #BC7B6F;
    border-radius: 25px;
}

.inputs {
    border: 3px solid #BC7B6F;
    border-radius: 25px;
    input {
        border: 3px solid #BC7B6F;
        background: #f5f5f5;
        border-radius: 25px;
        padding: 5px 15px;
    }
    textarea {
        border: 3px solid #BC7B6F;
        background: #f5f5f5;
        border-radius: 25px;
        padding: 5px 15px;
    }
}
.btn {

}

</style>