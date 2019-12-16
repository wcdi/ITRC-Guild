<template>
  <div class="MainBox">
    <nuxt-link to="/ranking">ランキング</nuxt-link>
    <nuxt-link to="/mypage">マイページ</nuxt-link>
    <nuxt-link to="/order">受注一覧</nuxt-link>
  </div>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
.Main {
  &Box {
    height: 100vh;
    display: flex;
    justify-content: space-around;
    flex-direction: column;
    align-items: center;
  }
}
</style>
