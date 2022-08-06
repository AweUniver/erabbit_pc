<template>
  <!-- 顶部 -->
  <app-navbar></app-navbar>
  <!-- 头部 -->
  <app-header></app-header>
  <!-- 吸顶头部 -->
  <app-header-sticky></app-header-sticky>
  <!-- 内容 -->
  <div class="app-body">
    <RouterView />
  </div>
  <!-- 底部 -->
  <app-footer></app-footer>
</template>

<script>
import AppNavbar from '@/components/app-navbar.vue'
import AppHeader from '@/components/app-header.vue'
import AppFooter from '@/components/app-footer.vue'
import AppHeaderSticky from '@/components/app-header-sticky.vue'
import { useStore } from 'vuex'
export default {
  name: 'layout',
  components: { AppNavbar, AppHeader, AppFooter, AppHeaderSticky },
  setup () {
    const store = useStore()
    store.dispatch('category/getList')
  }
}
</script>

<style scoped lang="less"></style>
