<template>
  <div class="job">
    <!-- mainJob -->
    <div v-if="mainJob == 'front'">
      <img src="~/assets/images/weapon/sword.svg" />
      <!-- <p>{{mainJob}}</p> -->
    </div>
    <div v-if="mainJob == 'infra'">
      <img src="~/assets/images/weapon/hammer.svg" />
      <p>{{mainJob}}</p>
    </div>
    <div v-if="mainJob == 'securyty'">
      <img src="~/assets/images/weapon/shield.svg" />
      <p>{{mainJob}}</p>
    </div>
    <div v-if="mainJob == 'backend'">
      <img src="~/assets/images/weapon/gun.svg" />
      <p>{{mainJob}}</p>
    </div>

    <!-- jubJob -->
    <div v-for="(item, index) in job" :key="index">
      <div v-if="item.name == 'front'">
        <img src="~/assets/images/weapon/sword.svg" />
      </div>
      <div v-if="item.name == 'infra'">
        <img src="~/assets/images/weapon/hammer.svg" />
      </div>
      <div v-if="item.name == 'securyty'">
        <img src="~/assets/images/weapon/shield.svg" />
      </div>
      <div v-if="item.name == 'backend'">
        <img src="~/assets/images/weapon/gun.svg" />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["mainJob", "job"]
};
</script>

<style lang="scss" scoped>
.job {
  display: flex;
  /deep/ img {
    height: 3rem;
    width: 3rem;
  }
}
</style>