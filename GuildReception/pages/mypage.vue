<template>
  <div>
    <div v-for="(item, index) in contents" :key="index" class="mypageStatusBox">
      <div>
        <img :src="item.image" />
      </div>
      <div>
        <h2>{{item.name}}</h2>
        <div class="mypageJobBox">
          <div class="mypageJob">
            <p>得意</p>
            <job :mainJob="item.mainJob" />
          </div>
          <div class="mypageJob">
            <p>装備可</p>
            <job :job="item.job" />
          </div>
        </div>
        <p>戦闘力: {{item.point}}</p>
        <div>
          <div class="mypagePointInfoBox">
            <div class="mypagePointInfo">
              <p class="mypagePointInfoName">物攻</p>
              <p class="mypagePointInfoNumber">{{physicalAttack}}</p>
            </div>
            <div class="mypagePointInfo">
              <p class="mypagePointInfoName">物防</p>
              <p class="mypagePointInfoNumber">{{physicalDefense}}</p>
            </div>
          </div>
          <div class="mypagePointInfoBox">
            <div class="mypagePointInfo">
              <p class="mypagePointInfoName">魔攻</p>
              <p class="mypagePointInfoNumber">{{magicAttack}}</p>
            </div>
            <div class="mypagePointInfo">
              <p class="mypagePointInfoName">魔防</p>
              <p class="mypagePointInfoNumber">{{magicDefense}}</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import job from "~/components/mypage/job.vue";

export default {
  components: {
    job
  },
  data() {
    return {
      contents: [
        {
          name: "nanoka",
          image:
            "https://ca.slack-edge.com/TH9SKRH3N-UKCJAKEA2-a1f927f2a579-512",
          mainJob: "front",
          job: [
            {
              name: "front"
            },
            {
              name: "backend"
            },
            {
              name: "infra"
            },
            {
              name: "securyty"
            }
          ],
          point: "2000"
        }
      ],
      physicalAttack: "",
      physicalDefense: "",
      magicAttack: "",
      magicDefense: ""
    };
  },
  mounted() {
    let randRange = (min, max) =>
      Math.floor(Math.random() * (max - min + 1) + min);
    this.physicalAttack = randRange(1, this.contents[0].point);
    this.physicalDefense = randRange(
      1,
      this.contents[0].point - this.physicalAttack
    );
    this.magicAttack = randRange(
      1,
      this.contents[0].point - this.physicalAttack - this.physicalDefense
    );
    this.magicDefense =
      this.contents[0].point -
      this.physicalAttack -
      this.physicalDefense -
      this.magicAttack;
  }
};
</script>


<style lang="scss" scoped>
.mypage {
  &Status {
    &Box {
      display: flex;
    }
  }
  &Job {
    display: flex;
    align-items: center;
    &Box {
      display: flex;
      border-bottom: 1px solid;
    }
  }
  &Point {
    &Info {
      display: flex;
      align-items: center;
      &Box{
        display: flex;
      }
      &Name{
        background-color: #734e30;
        color: #fff;
        padding: 1rem;
      }
      &Number{
        background-color:#90623c;
        color: #fff;
        padding: 1rem;
      }
    }
  }
}
</style>