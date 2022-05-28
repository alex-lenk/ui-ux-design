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
    <LogoComponent class-logo="header__logo" :alt="logoAltText"/>

    <div class="header__toggle" :class="{'header__toggle-open': isActiveMenu}" @click="toggleMenu">
      <span class="header__toggle-decor"></span>
    </div>
  </header>

  <nav class="nav" :class="{nav__open: isActiveMenu}" @click.self="toggleMenu">
    <div class="nav__inner">
      <LogoComponent class-logo="nav__logo" :alt="logoAltText"/>

      <ul class="nav__menu">
        <router-link to="/" custom v-slot="{ href, isActive }">
          <li class="nav__menu-item" :class="[isActive && 'nav__menu-active']">
            <a class="nav__link" :href="href">Главная</a>
          </li>
        </router-link>

        <router-link to="/portfolio" custom v-slot="{ href, isActive }">
          <li class="nav__menu-item" :class="[isActive && 'nav__menu-active']">
            <a class="nav__link" :href="href">Портфолио</a>
          </li>
        </router-link>

        <router-link to="/skill" custom v-slot="{ href, isActive }">
          <li class="nav__menu-item" :class="[isActive && 'nav__menu-active']">
            <a class="nav__link" :href="href">Скиллсет</a>
          </li>
        </router-link>

        <router-link to="/about" custom v-slot="{ href, isActive }">
          <li class="nav__menu-item" :class="[isActive && 'nav__menu-active']">
            <a class="nav__link" :href="href">Обо мне</a>
          </li>
        </router-link>

        <router-link to="/contacts" custom v-slot="{ href, isActive }">
          <li class="nav__menu-item" :class="[isActive && 'nav__menu-active']">
            <a class="nav__link" :href="href">Контакты</a>
          </li>
        </router-link>
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
        ©2017 — 2022
        <span class="text__nowrap">ui-ux-design.ru</span>
        <br>
        права сохранены
      </footer>
    </div>
  </nav>

  <RouterView />
</template>

<style lang="scss">
@import '/src/assets/styles/styles.scss';
</style>
