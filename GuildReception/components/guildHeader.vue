<template>
  <div class="guildHeader">
    <div class="guildHeaderUser">
      <img
        src="https://ca.slack-edge.com/TH9SKRH3N-UK9R8FE3F-5fe3cf7bfcaf-512"
        class="guildHeaderUserImage"
      />
      <div class="guildHeaderUserNameBox">
        <p class="guildHeaderUserPoint">Guild Master</p>
        <h2 class="guildHeaderUserName">medjed</h2>
      </div>
    </div>
    <div v-if="isHamburger">
      <a class="guildHeaderHamburgerMenu" href="#">
        <nuxt-link to="/">home</nuxt-link>
        <nuxt-link to="/order">クエスト一覧</nuxt-link>
        <nuxt-link to="/mypage">マイページ</nuxt-link>
        <nuxt-link to="/myorder">受注クエスト一覧</nuxt-link>
        <nuxt-link to="/help">ヘルプ</nuxt-link>
      </a>
    </div>
    <div v-else class="guildHeaderMenu">
      <nuxt-link to="/">home</nuxt-link>
      <nuxt-link to="/order">クエスト一覧</nuxt-link>
      <nuxt-link to="/mypage">マイページ</nuxt-link>
      <nuxt-link to="/myorder">受注クエスト一覧</nuxt-link>
      <nuxt-link to="/help">ヘルプ</nuxt-link>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isHamburger: false
    };
  }
};
</script>

<style lang="scss" scoped>
.guild {
  &Header {
    height: 10vh;
    background-color: #222;
    padding: 1rem;
    display: flex;
    justify-content: space-between;
    align-items: center;
    &User {
      display: flex;
      align-items: center;
      &Image {
        height: 3rem;
        width: 3rem;
        border-radius: 90%;
      }
      &Name {
        color: #fff;
        &Box {
          margin-left: 1rem;
          display: flex;
          flex-direction: column;
          align-items: center;
        }
      }
      &Point {
        color: #acb6e5;
        background: -webkit-linear-gradient(0deg, #acb6e5, #86fde8);
        -webkit-background-clip: text;
        -webkit-text-fill-color: transparent;
      }
    }
    &Menu {
      /deep/ a {
        color: #fff;
        font-weight: bold;
        text-decoration: none;
        margin: 0 1rem;
        display: inline-block;
        &::after {
          content: "";
          width: 0;
          transition: all 0.3s ease;
          border-bottom: 2px solid #000;
          display: block;
        }
        &:hover {
          &::after {
            width: 100%;
            border-bottom: 2px solid;
            border-color: #66ffcc;
          }
        }
      }
    }
    &Hamburger {
      &Menu {
      }
    }
  }
}
</style>
