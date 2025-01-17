<template>
  <!-- 網頁最外層 -->
  <v-app>
    <!-- 導覽列 -->
    <v-app-bar>
      <v-container class="d-flex align-center">
        <v-app-bar-title>番茄鍾</v-app-bar-title>
        <v-btn prepend-icon="mdi-home" to="/"> 首頁 </v-btn>
        <v-btn prepend-icon="mdi-format-list-bulleted" to="/list"> 事項 </v-btn>
        <v-btn prepend-icon="mdi-cog" to="/settings"> 設定 </v-btn>
      </v-container>
    </v-app-bar>
    <!-- 路由 -->
    <v-main class="me">
      <!--
        slot = 插槽 = 自訂元件內的某部分HTML
        v-solt = "元件插槽提供的可用變數"
        Component = 目前路由應該顯示的元件
      -->
      <router-view v-slot="{ Component }">
        <!--
          keep-alive 包住的元件不會被銷毀
          include 指定保留的元件
          component = 動態元件
          is = 要使用的元件
        -->
        <keep-alive include="index">
          <component :is="Component"></component>
        </keep-alive>
      </router-view>
    </v-main>
  </v-app>
</template>

<style>
.me {
  /* background: url('./assets/192846.png') center/cover ; */
  background: linear-gradient(to left bottom, red, transparent);
}
</style>
