<template>
  <a :class="classLogo" href="/">
    <img src="/src/assets/img/logo.svg" :alt="alt">
  </a>
</template>
<script>
export default {
  props: ['alt', 'classLogo'],
}
</script>
