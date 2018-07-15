<template>
  <div class="contanier">
    <header>
      <span style="cursor: pointer;"  @click="index">太平洋保险首页 | 太平洋旗下业务</span>
      <span>请登录 | 免费注册</span>
    </header>
    <div class="page-title">
      <span>健康商城</span>
    </div>
    <div class="content">
      <div class="list-box">
        <div class="title-box">
          <div class="rect-bag"></div>
          <div class="rect-small"></div>
          <span class="title">体检套餐</span>
          <div class="rect-small"></div>
          <div class="rect-bag"></div>
        </div>
        <el-row style="margin-top: 20px;" :gutter="20">
          <el-col :span="8">
            <HealthCard></HealthCard>
          </el-col>
          <el-col :span="8">
            <HealthCard></HealthCard>
          </el-col>
          <el-col :span="8">
            <HealthCard></HealthCard>
          </el-col>
        </el-row>
        <el-row style="margin-top: 20px;" :gutter="20">
          <el-col :span="8">
            <HealthCard></HealthCard>
          </el-col>
          <el-col :span="8">
            <HealthCard></HealthCard>
          </el-col>
          <el-col :span="8">
            <HealthCard></HealthCard>
          </el-col>
        </el-row>
      </div>
      <div class="list-box">
        <div class="title-box">
          <div class="rect-bag"></div>
          <div class="rect-small"></div>
          <span class="title">商业保险</span>
          <div class="rect-small"></div>
          <div class="rect-bag"></div>
        </div>
        <el-row style="margin-top: 20px;" :gutter="20">
          <el-col :span="8">
            <HealthCard color="#DBB17E"></HealthCard>
          </el-col>
          <el-col :span="8">
            <HealthCard color="#DBB17E"></HealthCard>
          </el-col>
          <el-col :span="8">
            <HealthCard color="#DBB17E"></HealthCard>
          </el-col>
        </el-row>
        <el-row style="margin-top: 20px;" :gutter="20">
          <el-col :span="8">
            <HealthCard color="#DBB17E"></HealthCard>
          </el-col>
          <el-col :span="8">
            <HealthCard color="#DBB17E"></HealthCard>
          </el-col>
          <el-col :span="8">
            <HealthCard color="#DBB17E"></HealthCard>
          </el-col>
        </el-row>
      </div>
    </div>
    <div class="content-bottom">
      <div class="list-box">
        <div class="title-box">
          <div class="rect-bag"></div>
          <div class="rect-small"></div>
          <span class="title">医疗器械</span>
          <div class="rect-small"></div>
          <div class="rect-bag"></div>
        </div>
        <el-row style="margin-top: 20px;" :gutter="20">
          <el-col :span="6">
            <ApparatusCard></ApparatusCard>
          </el-col>
          <el-col :span="6">
            <ApparatusCard></ApparatusCard>
          </el-col>
          <el-col :span="6">
            <ApparatusCard></ApparatusCard>
          </el-col>
          <el-col :span="6">
            <ApparatusCard></ApparatusCard>
          </el-col>
        </el-row>
        <el-row style="margin-top: 20px;" :gutter="20">
          <el-col :span="6">
            <ApparatusCard></ApparatusCard>
          </el-col>
          <el-col :span="6">
            <ApparatusCard></ApparatusCard>
          </el-col>
          <el-col :span="6">
            <ApparatusCard></ApparatusCard>
          </el-col>
          <el-col :span="6">
            <ApparatusCard></ApparatusCard>
          </el-col>
        </el-row>

      </div>
    </div>
    <div class="content-bottom">
      <div class="list-box">
        <div class="title-box">
          <div class="rect-bag"></div>
          <div class="rect-small"></div>
          <span class="title">养生保健</span>
          <div class="rect-small"></div>
          <div class="rect-bag"></div>
        </div>
        <el-row style="margin-top: 20px;" :gutter="20">
          <el-col :span="6">
            <ApparatusCard></ApparatusCard>
          </el-col>
          <el-col :span="6">
            <ApparatusCard></ApparatusCard>
          </el-col>
          <el-col :span="6">
            <ApparatusCard></ApparatusCard>
          </el-col>
          <el-col :span="6">
            <ApparatusCard></ApparatusCard>
          </el-col>
        </el-row>
      </div>
    </div>
  </div>
</template>
<script>
import HealthCard from "../common/health-card";
import ApparatusCard from "../common/apparatus-card";

export default {
  components: {
    HealthCard,
    ApparatusCard
  },
  methods: {
    index() {
      this.$router.push({ path: "/" });
    }
  }
};
</script>
<style scoped>
.contanier {
  background: #efefef;
  padding-bottom: 40px;
}
header {
  background: #efefef;
  padding: 0 154px;
  height: 35px;
  line-height: 35px;
  font-size: 12px;
  color: #666666;
  display: flex;
  justify-content: space-between;
}
.page-title {
  padding: 0 154px;
  height: 86px;
  line-height: 86px;
  font-size: 22px;
  color: #3371d0;
  background-color: #fff;
}
.content {
  margin: 20px 154px;
  background-color: #fff;
}
.content-bottom {
  margin: 20px 154px;
}
.content-bottom .list-box {
  padding: 0px;
  box-sizing: content-box;
}
.list-box {
  padding: 20px;
  box-sizing: content-box;
}
.title-box {
  height: 40px;
  line-height: 40px;
  text-align: center;
}
.title {
  font-size: 28px;
  color: #333333;
  vertical-align: middle;
  margin: 0 10px;
}
.rect-small {
  width: 9px;
  height: 9px;
  display: inline-block;
  transform: rotate(-45deg);
  background: #2873c8;
  vertical-align: middle;
  margin: 0 6px;
}
.rect-bag {
  width: 14px;
  height: 14px;
  display: inline-block;
  transform: rotate(-45deg);
  background: #2873c8;
  vertical-align: middle;
}
</style>
