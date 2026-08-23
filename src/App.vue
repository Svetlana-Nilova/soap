<script setup>
import { ref } from 'vue'
import Promo from "./components/promo.vue"
import About from "./components/about.vue"
import Catalog from "./components/catalog.vue"
import Contacts from "./components/contacts.vue"
import Reviews from "./components/reviews.vue"

const showMenu = ref(false)
const toggleMenu = () => { showMenu.value = !showMenu.value }
const closeMenu = () => { showMenu.value = false }
</script>

<template>
  <header>
    <div class="flex flex_header">
      <div class="logo">
        <a href="./App.vue">
          <img src="./assets/logo.png" alt="логотип">
        </a>
      </div>

      <!-- Навигация -->
      <nav :class="{ active: showMenu }">
        <ul class="flex">
          <li class="close" @click="closeMenu" :class="{ active: showMenu }"><button>закрыть</button></li>
          <li><a href="#About" @click="closeMenu">О нас</a></li>
          <li><a href="#Catalog" @click="closeMenu">Наше мыло</a></li>
          <li><a href="#Reviews" @click="closeMenu">Отзывы</a></li>
          <li><a href="#Contacts" @click="closeMenu">Контакты</a></li>
        </ul>
      </nav>

      <div class="tel flex">
        <img src="./assets/phone.svg" alt="">
        <a href="tel:+78005553535">+7(966)-888-55-55</a>
      </div>

      <!-- Бургер -->
      <button class="burger" @click="toggleMenu" :class="{ active: showMenu }">
        <span></span><span></span><span></span>
      </button>
    </div>
  </header>

  <main>
    <Promo />
    <div class="antverpen" id="About">

      <About />
    </div>
    <div class="antverpen" id="Catalog">

      <Catalog />
    </div>
    <div class="antverpen" id="Reviews">

      <Reviews />
    </div>
    <div class="antverpen" id="Contacts">
      <Contacts />

    </div>

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
/* ===== Общие ===== */
.flex {
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
}

li a {
  padding: 0 15px;
  border: 1px solid #BC7B6F;
  border-radius: 25px;
  text-decoration: none;
  color: #BC7B6F;
}

li a:hover {
  background-color: #BC7B6F;
  border-color: #BC7B6F;
  color: #F5F5F5;
}

a {
  text-decoration: none;
  color: #BC7B6F;
}

/* ===== Шапка ===== */
.flex_header {
  justify-content: space-around;
  align-items: center;
  text-transform: uppercase;
  border-bottom: 3px solid #BC7B6F;
  padding: 8px 20px;
  position: relative;
}

.logo img {
  width: 75px;
}

/* ===== Навигация ===== */
nav ul {
  display: flex;
  align-items: center;
}

/* ===== Бургер ===== */
.burger {
  display: none;
  flex-direction: column;
  justify-content: space-between;
  width: 30px;
  height: 22px;
  background: transparent;
  border: none;
  cursor: pointer;
  padding: 0;
  margin-left: 15px;
}

.burger span {
  display: block;
  width: 100%;
  height: 3px;
  background: #BC7B6F;
  border-radius: 3px;
  transition: 0.3s ease;
}

.burger.active span:nth-child(1) {
  transform: translateY(9px) rotate(45deg);
}

.burger.active span:nth-child(2) {
  opacity: 0;
}

.burger.active span:nth-child(3) {
  transform: translateY(-9px) rotate(-45deg);
}

/* ===== main фон ===== */
main {
  position: relative;
  background: url(./assets/backg4.svg) center/contain;
  border-radius: 60px;
  min-height: 100vh;
}

main::before {
  content: '';
  position: absolute;
  inset: 0;
  border-radius: 60px;
  background: url(./assets/backg4.svg) center/contain;
  pointer-events: none;
  z-index: 0;
}

main>* {
  position: relative;
  z-index: 1;
}

/* ===== Подвал ===== */
.flex_footer {
  justify-content: space-around;
  align-items: center;
  background-color: #BC7B6F;
  padding: 15px 20px;
  flex-wrap: wrap;
  gap: 10px;
}

.flex_footer p,
.flex_footer a {
  color: #fff;
}
.flex_footer p {
  order: 1;
}

.icons a {
  display: inline-block;
  width: 50px;
  height: 50px;
}

.tg {
  background-image: url(./assets/tg.svg);
  margin-right: 27px;
}

.vk {
  background-image: url(./assets/vk.svg);
  margin-left: 27px;
}

/* ===== Адаптив ===== */
@media (max-width: 1024px) {
  .flex_header {
    justify-content: space-between;
    padding: 8px 15px;
  }

  .burger {
    display: flex;
  }

  nav {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100vh;
    background: rgba(245, 245, 245, 0.97);
    backdrop-filter: blur(6px);
    display: flex;
    align-items: center;
    justify-content: center;
    transform: translateX(100%);
    transition: transform 0.4s ease;
    z-index: 999;
  }

  nav.active {
    transform: translateX(0);
  }

  nav ul {
    flex-direction: column;
    gap: 30px;
  }

  nav ul li {
    margin: 0;
  }

  nav ul li a {
    font-size: 22px;
    padding: 10px 30px;
    border-width: 2px;
  }

  .tel {
    margin-right: 10px;
  }

  .tel a {
    font-size: 14px;
  }

  /* подвал */
  .flex_footer {
    text-align: center;
  }

  .icons {
    margin-bottom: 5px;
  }

  main {
    border-radius: 30px;
    margin: 6px;
  }
}

@media (max-width: 480px) {
  .logo img {
    width: 70px;
  }

  .tel img {
    width: 20px;
  }

  .tel a {
    font-size: 12px;
  }

  .burger {
    width: 26px;
    height: 18px;
  }

  nav ul li a {
    font-size: 18px;
    padding: 8px 20px;
  }

  .flex_footer p {
    font-size: 14px;
  }

  .icons a {
    width: 40px;
    height: 40px;
    background-size: contain;
  }
}
</style>