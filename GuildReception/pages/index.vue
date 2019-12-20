<template>
  <div style="margin-bottom: 7.4rem;">
    <div class="mainTitleBoxBackground">
      <div class="mainTitleBox">
        <h1 class="mainTitleText">🔥Guild System🔥</h1>
      </div>
    </div>
    <marquee class="mainInfo">
      <span style="color:#f00;">お知らせ‼︎</span> 進捗率がとてもよくありません。早く作ってしまいましょう。つか、ここのお知らせって何書いて良いのかよくわら感よなぁ。本当に。だらだら書いているからこれで良いのかな。
    </marquee>
    <ranking />
    <div class="tabBar">
      <nuxt-link to="/">ホーム</nuxt-link>
      <nuxt-link to="/order">クエスト一覧</nuxt-link>
      <nuxt-link to="/mypage">マイページ</nuxt-link>
      <nuxt-link to="/myorder">クエスト管理</nuxt-link>
      <nuxt-link to="/help">ヘルプ</nuxt-link>
    </div>
  </div>
</template>

<script>
import ranking from "~/components/main/ranking.vue";

export default {
  components: {
    ranking
  }
};
</script>

<style lang="scss" scoped>
.main {
  &Title {
    &Box {
      position: absolute;
      width: 100%;
      height: 70vh;
      display: flex;
      justify-content: center;
      align-items: center;
      &Background {
        height: 70vh;
        background-image: url("~@/assets/images/guildBackground.jpg");
        background-repeat: no-repeat;
        background-size: cover;
        &::before {
          background-color: rgba(0, 0, 0, 0.5);
          position: absolute;
          top: 0;
          right: 0;
          bottom: 30vh;
          left: 0;
          content: " ";
        }
      }
    }
    &Text {
      color: #fff;
    }
  }
  &Info {
    padding: 2.2rem 1rem;
    background: whitesmoke; /*背景色*/
    border-left: double 7px #4ec4d3; /*左線*/
    border-right: double 7px #4ec4d3;
    color: #474747;
    // color:#fff;
  }
}

.tabBar {
  display: flex;
  justify-content: space-around;
  padding: 3rem 0;
  background-color: rgba(23, 155, 255, 0.75);
  position: fixed;
  width: 100%;
  bottom: 0;
}
</style>
