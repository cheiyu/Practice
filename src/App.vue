<script setup>
import { RouterLink, RouterView } from 'vue-router'
import HelloWorld from './components/HelloWorld.vue'
import Button from './components/Button/Button.vue'
import DeleteIcon from '@/assets/icons/delete.svg'
import FilterIcon from '@/assets/icons/filter.svg'
import EditIcon from '@/assets/icons/edit.svg'

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

    <Button theme="primary" size="md">送出</Button>
    <Button theme="info" size="md">評價</Button>
    <Button theme="secondary" size="md">取消</Button>
    <Button :onClick="aloha" theme="primary" size="lg">GO</Button>
    <Button theme="info" size="md" disabled="disabled">編輯</Button>
    <Button :icon="DeleteIcon" theme="secondary" size="sm">刪除</Button>
    <Button :icon="FilterIcon" theme="secondary" size="sm">篩選</Button>
    <Button :icon="EditIcon" theme="info" size="sm">編輯</Button>
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

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }

  nav {
    text-align: left;
    margin-left: -1rem;
    font-size: 1rem;

    padding: 1rem 0;
    margin-top: 1rem;
  }
}
</style>
