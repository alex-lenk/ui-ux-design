<script setup>
import {ref} from 'vue'
import BehanceIcon from '/src/components/icons/IconBehance.vue'
import DribbleIcon from '/src/components/icons/IconDribble.vue'
import LogoComponent from '/src/components/LogoLogoComponent.vue'
//import {RouterLink, RouterView} from 'vue-router'
//import HelloWorld from '/src/components/HelloWorld.vue'

const logoAltText = ref('Ui Ux design')
const isActiveMenu = ref(false)

function toggleMenu() {
  isActiveMenu.value = !isActiveMenu.value
  console.log('click')
}
</script>

<template>
  <header class="header">
    <LogoComponent class-logo="header__logo" :alt="logoAltText" />

    <div class="header__toggle" @click="toggleMenu"></div>
  </header>

  <nav class="nav" :class="{nav__open: isActiveMenu}" @click.self="toggleMenu">
    <div class="nav__inner">
      <LogoComponent class-logo="nav__logo" :alt="logoAltText" />

      <ul class="nav__menu">
        <li class="nav__menu-item">
          <RouterLink class="nav__menu-link nav__link" to="/">Главная</RouterLink>
        </li>
        <li class="nav__menu-item">
          <RouterLink class="nav__menu-link nav__link" to="/portfolio">Портфолио</RouterLink>
        </li>
        <li class="nav__menu-item">
          <RouterLink class="nav__menu-link nav__link" to="/skill">Скиллсет</RouterLink>
        </li>
        <li class="nav__menu-item">
          <RouterLink class="nav__menu-link nav__link" to="/about">Обо мне</RouterLink>
        </li>
        <li class="nav__menu-item">
          <RouterLink class="nav__menu-link nav__link" to="/contacts">Контакты</RouterLink>
        </li>
      </ul>

      <div class="nav__social">
        <a href="#" class="nav__link" rel="nofollow" target="_blank">
          <BehanceIcon/>
        </a>
        <a href="#" class="nav__link" rel="nofollow" target="_blank">
          <DribbleIcon/>
        </a>
      </div>

      <footer class="nav__footer">
        ©2017 — 2022<br>
        ui-ux-design.ru<br>
        права сохранены
      </footer>
    </div>
  </nav>

  <RouterView />
</template>

<style lang="scss">
@import '/src/assets/styles/styles.scss';
</style>
