<script setup>
import facebookButtom from './components/icons/facebookButtom.vue';
import instagramButtom from './components/icons/instagramButtom.vue';
</script>

<template>
  <header class="navbar">
    <div class="navbar-left">
      <img class="logo" src="./assets/logo.png" />
    </div>
    <nav class="navbar-right"> 
      <router-link to="/">首頁HOME</router-link>
      |
      <router-link to="/schedule">日程SCHEDULE</router-link>
      |
      <router-link to="/theme">主題THEME</router-link>
      |
      <router-link to="/posts">貼文POSTS</router-link>
      |
      <router-link to="/album">相簿ALBUM</router-link>
      |
    </nav>
    <div class="navbar-icons">
      <facebook-buttom />
      <instagram-buttom />
    </div>
  </header>

  <div class="banner">
    <img src="./assets/banner.png" alt="Banner" />
  </div>

  <main class="main-content">
    <router-view />
  </main>
</template>



<style scoped>

/* 🔷 導覽列 */
.navbar {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  z-index: 10;
  display: flex;
  justify-content: space-between;
  align-items: center;
  background-color: #1e1e1e; /* 導覽列背景顏色 */
  padding: 0.5rem 1rem;
  height: 80px;
  border-bottom: 2px solid #444; /* 可選：下方加一道線 */
}

.logo {
  width: 64px;
  height: 64px;
  object-fit: cover;
  border-radius: 8px;
}

.navbar-left {
  display: flex;
  align-items: center;
}

.navbar-right a {
  color: #42b983;
  text-decoration: none;
  font-weight: bold;
  transition: color 0.3s;
}

.navbar-right a:hover {
  color: #89e2b0;
}


/* 🔶 橫幅圖片區塊 */
.banner {
  position: absolute;
  top: 80px;
  left: 0;
  width: 100%;
  height: 250px;        /* 限制高度為 X px */
  overflow: hidden;     
  z-index: 0;
  pointer-events: none;
}

.banner img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  object-position: center 48%;  /* 圖片位置中心調整 */
  display: block;
}

/* 🔶 內容區域 */
.main-content {
  position: absolute;
  top: 330px;
  left: 50%;
  transform: translateX(-50%);
  width: 80%;
  padding: 1rem 2rem;

}

.navbar-icons {
  display: flex;
  gap: 10px;
  align-items: center;
}
/* * {
  outline: 1px solid red;
}
 偵錯程式*/
</style>
