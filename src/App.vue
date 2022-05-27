<script setup>
import {RouterLink, RouterView} from 'vue-router'
import HelloWorld from '/src/components/HelloWorld.vue'
import BehanceIcon from '/src/components/icons/IconBehance.vue'
import DribbleIcon from '/src/components/icons/IconDribble.vue'
</script>

<template>
  <nav class="nav">
    <a href="/" class="nav__logo">
      <img alt="Ui Ux design" src="src/assets/img/logo.svg">
    </a>

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
  </nav>

  <RouterView/>
</template>

<style lang="scss">
@import '/src/assets/styles/styles.scss';
</style>
