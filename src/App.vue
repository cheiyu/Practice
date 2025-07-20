<script setup>
import { RouterLink, RouterView } from 'vue-router'
import HelloWorld from './components/HelloWorld.vue'
import Button from './components/Button/Button.vue'
import DeleteIcon from '@/assets/icons/delete.svg'
import FilterIcon from '@/assets/icons/filter.svg'
import EditIcon from '@/assets/icons/edit.svg'
import NotifyIcon from '@/assets/icons/notification.svg'
import SortIcon from '@/assets/icons/sort.svg'

const aloha = () => {
  alert('阿囉哈')
}
</script>

<template>
  <header>
    <!-- <img alt="Vue logo" class="logo" src="@/assets/logo.svg" width="125" height="125" /> -->

    <div class="wrapper">
      <!-- <HelloWorld msg="You did it!" /> -->

      <nav>
        <RouterLink to="/">Home</RouterLink>
        <RouterLink to="/about">About</RouterLink>
      </nav>
    </div>

    <Button :onClick="aloha" theme="primary" size="md">送出</Button>
    <br />
    <Button theme="primary" size="md">評價</Button>
    <Button theme="secondary" size="md" disabled="disabled">取消</Button>
    <br />
    <Button isFull="true" theme="primary" size="md">GO</Button>
    <br />
    <Button iconPosition="right" :icon="FilterIcon" theme="secondary" size="sm">篩選</Button>
    <Button iconPosition="right" :icon="SortIcon" theme="secondary" size="sm">排序</Button>
    <br />
    <Button :icon="NotifyIcon" theme="primary" size="lg">通知訊息</Button>
    <Button :icon="EditIcon" theme="info" size="lg">編輯檔案</Button>
  </header>

  <RouterView />
</template>

<style scoped>
header {
  line-height: 1.5;
  max-height: 100vh;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

nav {
  width: 100%;
  font-size: 12px;
  text-align: center;
  margin-top: 2rem;
}

nav a.router-link-exact-active {
  color: var(--color-text);
}

nav a.router-link-exact-active:hover {
  background-color: transparent;
}

nav a {
  display: inline-block;
  padding: 0 1rem;
  border-left: 1px solid var(--color-border);
}

nav a:first-of-type {
  border: 0;
}
</style>
