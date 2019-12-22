<template>
  <div class="ranking">
    <h1 class="rankingTitle">👑ランキング👑</h1>
    <div v-for="(content, index) in contents" :key="index" class="rankingBox">
      <div class="rankingTopBox">
        <div v-for="(item, index) in content.top" :key="index" class="rankingTopContents">
          <div class="rankingTopNumberBox">
            <div v-if="(index+1) % 3 == 1" class="crownBox" style="background: #ffc668;">
              <img src="~/assets/images/crown.svg" class="crownStyle" />
            </div>
            <div v-else-if="(index+1) % 3 == 2" class="crownBox" style="background: #BDC3C9">
              <img src="~/assets/images/crown.svg" class="crownStyle" />
            </div>
            <div v-else-if="(index+1) % 3 == 0" class="crownBox" style="background: #C47022">
              <img src="~/assets/images/crown.svg" class="crownStyle" />
            </div>
            <h2 class="rankingTopNumber">{{index + 1}}</h2>
          </div>
          <div class="rankingTopItem">
            <div v-if="item.image">
              <img :src="item.image" class="rankingTopImage" />
            </div>
            <div v-else>
              <p>No Image</p>
            </div>
            <p>{{item.name}}</p>
          </div>
        </div>
      </div>
      <div class="rankingMember">
        <div v-for="(item, index) in content.member" :key="index" class="rankingMemberBox">
          <p class="rankingMemberNumber">{{index+4}}</p>
          <img :src="item.image" class="rankingMemberImage" />
          <p class="rankingMemberName">{{item.name}}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      contents: [
        {
          top: [
            {
              name: "nanoka",
              image:
                "https://ca.slack-edge.com/TH9SKRH3N-UKCJAKEA2-a1f927f2a579-512"
            },
            {
              name: "hashy0917",
              image:
                "https://ca.slack-edge.com/TH9SKRH3N-UH17UA197-a3f1abb637a8-512"
            },
            {
              name: "medjed",
              image:
                "https://ca.slack-edge.com/TH9SKRH3N-UK9R8FE3F-5fe3cf7bfcaf-512"
            }
          ],
          member: [
            {
              name: "RIN1208",
              image:
                "https://ca.slack-edge.com/TH9SKRH3N-UHBB3C4SJ-e3005d3de988-512"
            },
            {
              name: "moke",
              image:
                "https://ca.slack-edge.com/TH9SKRH3N-UH7F80B6C-8deaadc3cc91-512"
            },
            {
              name: "FariBot",
              image:
                "https://ca.slack-edge.com/TH9SKRH3N-UKC3M4T24-c8e7a971cd6b-512"
            },
            {
              name: "mckan",
              image:
                "https://ca.slack-edge.com/TH9SKRH3N-UHBBRHP5L-d107b93e4e05-512"
            }
          ]
        }
      ]
    };
  }
};
</script>

<style lang="scss" scoped>
.ranking {
  &Title {
    text-align: center;
    font-family: cursive;
    padding: 2rem 0;
  }
  background-color: #444;
  /deep/ h2,
  h1,
  p {
    color: #fff;
  }
  &Box {
    display: flex;
    flex-direction: column;
    padding: 2rem;
  }
  &Top {
    &Image {
      width: 12rem;
      height: 12rem;
      border-radius: 90%;
    }
    &Contents {
      display: flex;
    }
    &Box {
      display: flex;
      justify-content: space-around;
    }
    &Item {
      display: flex;
      flex-direction: column;
      align-items: center;
      margin-left: 1rem;
    }
    &Number {
      font-size: 2rem;
      &Box {
        display: flex;
        flex-direction: column;
        align-items: center;
      }
    }
  }

  &Member {
    margin-top: 4rem;
    &Image {
      width: 3rem;
      height: 3rem;
      border-radius: 90%;
    }
    &Box {
      display: flex;
      align-items: center;
      background-color: #222;
      padding: 1rem 0;
      margin-bottom: 5px;
    }
    &Number {
      font-size: 2rem;
      padding: 0 1rem;
    }
    &Name {
      padding: 0 1rem;
    }
  }
}

.crown {
  &Box {
    padding: 1rem 0.5rem 2rem 0.5rem;
    position: relative;
    &:after {
      position: absolute;
      content: "";
      width: 0px;
      height: 0px;
      z-index: 1;
      top: 50px;
      right: 13px;
      border-color: transparent #444 transparent transparent;
      border-style: solid;
      transform: rotateZ(90deg);
      border-width: 23px 20px 23px 0px;
    }
  }
  &Style {
    width: 2rem;
  }
}
</style>