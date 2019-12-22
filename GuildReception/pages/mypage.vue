<template>
  <div class="mypageBackground">
    <div class="mypageContent">
      <div class="mypageContentImageBox">
        <img
          class="mypageContentImage"
          src="https://ca.slack-edge.com/TH9SKRH3N-UK9R8FE3F-5fe3cf7bfcaf-512"
        />
      </div>
      <div class="mypageContentInfo">
        <p class="mypageATitle">
          称号: <span class="mypageATitleText">Guild Master</span>
        </p>
        <div class="mypageRank">
          <p>ランク: <span class="mypageRankText">歴戦のPythoner</span></p>
          <div class="experienceValueBar">
            <div class="experienceValue"></div>
          </div>
        </div>
        <p class="mypageContentName">
          名前: <span class="mypageContentNameStyle">medjed</span>
        </p>
        <p>一言コメント</p>
        <div class="mypageContentComment">
          <p>
            我が生涯に一片の悔い無し
          </p>
        </div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.mypage {
  &Background {
    background-color: #444;
    @media screen and (min-width: 980px) {
      height: 90vh;
    }
  }
  &Content {
    display: flex;
    padding: 5rem 0;
    @media screen and (max-width: 979px) {
      flex-direction: column;
      padding: 1rem;
    }
    justify-content: space-around;
    /deep/ p {
      color: #fff;
    }
    &Info {
      display: flex;
      flex-direction: column;
      @media screen and (min-width: 980px) {
        padding: 0 2rem;
        width: 50vw;
      }
    }
    &Image {
      @media screen and(min-width: 980px) {
        max-width: 512px;
        min-width: 512px;
        max-height: 512px;
        min-height: 512px;
      }
      max-width: 100%;
      &Box {
        display: flex;
        justify-content: center;
        @media screen and (max-width: 979px) {
          margin-bottom: 2rem;
        }
      }
    }
    &Name {
      margin-bottom: 2rem;
      &Style {
        font-size: 2rem;
      }
    }
    &Comment {
      background-color: #fff;
      height: 100%;
      padding: 1rem;
      display: flex;
      align-items: center;
      justify-content: center;
      /deep/ p {
        word-break: break-all;
        color: #222;
        font-weight: bold;
      }
    }
  }
  &ATitle {
    margin-bottom: 2rem;
    &Text {
      color: #acb6e5;
      background: -webkit-linear-gradient(0deg, #acb6e5, #86fde8);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      font-size: 2rem;
    }
  }
  &Rank {
    margin-bottom: 2rem;
    &Text {
      color: #f13f79;
      background: -webkit-linear-gradient(0deg, #f13f79, #ffc778);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      font-size: 2rem;
    }
  }
}

.experienceValue {
  height: 100%;
  width: 75%;
  background: -webkit-linear-gradient(-135deg, #e4a972, #9941d8);
  &Bar {
    height: 10px;
    width: 100%;
    background-color: #fff;
  }
}
</style>
