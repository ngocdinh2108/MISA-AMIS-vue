<template>
  <div class="wrap-body">
    <!-- Component sidebar -->
    <the-sidebar></the-sidebar>
    <!-- Phần nội dung bên phải bao gồm header và content -->
    <div class="wrap-right">
      <!-- Component header -->
      <the-header></the-header>
      <!-- Component content -->
      <the-content></the-content>
    </div>
  </div>
</template>

<script>
import TheContent from './components/layouts/TheContent.vue'
import TheHeader from './components/layouts/TheHeader.vue'
import TheSidebar from './components/layouts/TheSidebar.vue'

export default {
  name: 'App',
  components: {
    TheSidebar,
    TheHeader,
    TheContent
  }
}
</script>

<style>
@import url("./css/main.css");
@import url("./css/icon.css");
</style>
