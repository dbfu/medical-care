<template>
  <div class="card-box">
    <img v-if="type==1" src="../../assets/images/00018.jpg" />
    <img v-if="type==2" src="../../assets/images/00019.jpg" />
    <img v-if="type==3" src="../../assets/images/00020.jpg" />
    <img v-if="type==4" src="../../assets/images/00021.jpg" />
    <div v-if="type==1"  class="card-desc">轮椅</div>
    <div v-if="type==2"  class="card-desc">绷带</div>
    <div v-if="type==3"  class="card-desc">温度计</div>
    <div v-if="type==4"  class="card-desc">药罐</div>
  </div>
</template>
<script>
export default {
  props: {
    color: {
      default: "#13ba8e",
      type: String
    },
    type: String
  }
};
</script>
<style scoped>
.card-box {
  width: 100%;
  height: 374px;
  text-align: center;
  background-color: #fff;
  padding: 10px;
  box-sizing: border-box;
  border-radius: 4px;
}
.card-box img {
  height: 225px;
  width: 100%;
}
.card-desc {
  font-size: 26.14px;
  color: #333333;
  margin-top: 36px;
}
</style>
