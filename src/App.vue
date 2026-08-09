<script setup>

</script>

<template>
  <header>
    <div class="flex flex_header">
      <div class="logo">
        <img src="./assets/logo.png" alt="логотип">
      </div>
      <nav>
        <ul class="flex">
          <li><a href="#">О нас</a></li>
          <li><a href="#">Наше мыло</a></li>
          <li><a href="#">Отзывы</a></li>
          <li><a href="#">Контакты </a></li>
        </ul>
      </nav>
      <!-- <div class="tel"> -->
      <a href="tel:+78005553535">+7(966)-888-55-55</a>
      <!-- </div> -->
    </div>
  </header>
  <HelloWorld />
  <footer>
    <div class="flex flex_footer">
      <div class="icons">
        <a href="#"><img src="./assets/tg.png" alt="Телеграмм"></a>
        <a href="#"><img src="./assets/vk.png" alt="Вконтакте"></a>
      </div>
      <p>© 2026 Мыловар. Все права защищены.</p>
      <a href="tel:+78005553535">+7(966)-888-55-55</a>
    </div>
  </footer>
</template>

<style scoped>
/* Общие стили */
.flex {
  display: flex;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  padding: 0 15px;
  border: 1px solid #BC7B6F;
  border-radius: 25px;
  margin: 0 25px;
}

a {
  text-decoration: none;
  color: #BC7B6F;

}

/* Шапка */
.flex_header {
  justify-content: space-around;
  align-items: center;
  text-transform: uppercase;
  border-bottom: 3px solid #BC7B6F;
}

.logo {
  img {
    width: 100px;
  }
}


/* ?? */

/* Подвал */
.flex_footer {
  justify-content: space-around;
  align-items: center;
  background-color: #BC7B6F;
  p,a{
    color: #fff;
  }
  
}
</style>