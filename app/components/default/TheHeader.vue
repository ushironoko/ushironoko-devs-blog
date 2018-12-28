<template>
  <el-menu class="header" mode="vertical" :router="true" background-color="#01adb9" text-color="#fff" active-text-color="#FFF">
    <el-menu-item index="1" route="/">
      うしろのこ 開発ブログ
    </el-menu-item>
  </el-menu>
</template>

<style scoped>
  .header {
    position: sticky;
    top: 0;
  }
</style>
