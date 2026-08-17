<script setup>
import Promo from "./components/promo.vue"
import About from "./components/about.vue"
import Catalog from "./components/catalog.vue"
import Contacts from "./components/contacts.vue"
import Reviews from "./components/reviews.vue"
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
      <div class="tel flex">
        <img src="./assets/phone.svg" alt="">
        <a href="tel:+78005553535">+7(966)-888-55-55</a>
      </div>
    </div>
  </header>
  <main>

    <Promo />
    <About />
    <Catalog />
    <Reviews />
    <Contacts />
  </main>

  <footer>
    <div class="flex flex_footer">
      <div class="icons">
        <a href="#" class="tg"></a>
        <a href="#" class="vk"></a>
      </div>
      <p>© 2026 Мыловар. Все права защищены.</p>
      <div class="tel flex">
        <img src="./assets/phone_f.svg" alt="">
        <a href="tel:+78005553535">+7(966)-888-55-55</a>
      </div>
    </div>
  </footer>
</template>

<style scoped>
/* Общие стили */
.flex {
  /* display: flex; */
  height: 100%;
}

header {
  background-color: #F5F5F5;
  position: sticky;
  top: 0;
  z-index: 1000;
  width: 100%;
}

main {
  margin: 10px;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  margin: 0 25px;

  a {
    padding: 0 15px;
    border: 1px solid #BC7B6F;
    border-radius: 25px;
  }

  a:hover {
    background-color: #BC7B6F;
    border: 1px solid #BC7B6F;
    color: #F5F5F5;
  }
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


/* main */
/* #ece6e6 */
main {
  position: relative;
  background: url(./assets/backg4.svg) center/contain;
  /* background-color: #F4E4E4; */
  /* #ece6e6 */
  border-radius: 60px;
  min-height: 100vh;
}

main::before {
  content: '';
  position: absolute;
  inset: 0;
  border-radius: 60px;
  background: url(./assets/backg4.svg) center/contain;
  /* opacity: 0.6;           */
  pointer-events: none;
  z-index: 0;
}

main>* {
  position: relative;
  z-index: 1;
}

/* Подвал */
.flex_footer {
  justify-content: space-around;
  align-items: center;
  background-color: #BC7B6F;

  p,
  a {
    color: #fff;
  }

}

.icons {
  a {
    display: inline-block;
    width: 50px;
    height: 50px;
  }
}

.tg {
  background-image: url(./assets/tg.svg);
  margin: 0 27px 0 0;
}

.vk {
  background-image: url(./assets/vk.svg);
  margin: 0 0 0 27px;
}
</style>