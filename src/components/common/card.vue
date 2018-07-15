<template>
  <div class="contanier">
    <div class="title">
      <div class="left-box">
        <span class="line"></span>
        <span @click="skip" class="text">{{title}}</span>
      </div>
    </div>
    <div class="content">
      <slot name="content"></slot>
    </div>
  </div>
</template>
<script>
export default {
  props: {
    title: String
  },
  methods: {
    skip() {
      if(this.title == "健康商城") {
        this.$router.push({path: "/health-mall"})
      } if(this.title == "药品商城") {
        this.$router.push({path: "/drugShop"})
      }
    }
  }
};
</script>
<style scoped>
.contanier {
  width: 100%;
  padding: 0 105px;
  box-sizing: border-box;
}
.title {
  width: 100%;
  height: 60px;
  line-height: 60px;
  display: flex;
  justify-content: space-between;
}
.line {
  display: inline-block;
  height: 36px;
  width: 6px;
  background-color: rgba(22, 101, 192, 1);
  vertical-align: middle;
  margin-right: 10px;
}
.text {
  font-size: 18px;
  font-weight: bold;
  vertical-align: middle;
  cursor: pointer;
}
.right-box {
  padding-right: 40px;
  font-size: 18px;
  vertical-align: middle;
}
.content {
  padding: 20px 40px;
  overflow: hidden;
  box-sizing: border-box;
}
</style>
