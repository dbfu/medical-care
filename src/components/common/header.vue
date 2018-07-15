<template>
  <div class="contanier">
    <div class="top-box">
      <div @click="index" class="left-box">太平洋保险首页</div>
      <div class="right-box">{{ userName ? 'hello,' + userName : '请登陆 | 免费注册'}}</div>
    </div>
    <div class="bottom-box">
      <div @click="index" class="logo-box">
        <img src="../../assets/images/logo.png" class="logo" />
      </div>
      <ul class="nav">
        <li>首页</li>
        <li>社保服务</li>
        <li>医疗服务</li>
        <li>保障商城</li>
        <li>家庭医生</li>
        <li>医学助手</li>
        <li>关于我们</li>
      </ul>
      <div class="search-box">
        <Search></Search>
      </div>
    </div>
  </div>
</template>
<script>
import Search from "../common/search";
export default {
  components: {
    Search
  },
  props: {
    userName: {
      default: "",
      type: String
    }
  },
  methods: {
    index() {
      this.$router.push({ path: "/" });
    }
  }
};
</script>

<style  scoped>
.contanier {
  width: 100%;
}
.top-box {
  background-color: #efefef;
  height: 30px;
  line-height: 30px;
  display: flex;
  justify-content: space-between;
}
.left-box {
  font-family: PingFangSC-Regular;
  font-size: 12px;
  color: #666666;
  padding-left: 70px;
  cursor: pointer;
}
.right-box {
  color: #fff;
  padding-right: 70px;
  font-family: PingFangSC-Regular;
  font-size: 12px;
  color: #666666;
  vertical-align: middle;
}
.right-box a {
  font-family: PingFangSC-Regular;
  font-size: 12px;
  color: #666666;
  cursor: pointer;
  vertical-align: middle;
}
.right-box img {
  vertical-align: middle;
}
.bottom-box {
  display: flex;
  line-height: 80px;
  height: 80px;
  justify-content: center;
  background-color: #fff;
}
.logo-box {
  width: 300px;
  height: 80px;
  flex: 0 0 300px;
  text-align: center;
  line-height: 80px;
}
.logo {
  width: 160px;
  height: 46px;
  margin-top: 17px;
  cursor: pointer;
}
.nav {
  flex: 1;
  display: flex;
  list-style: none;
}
.nav li {
  flex: 1;
  font-size: 18px;
  font-weight: bold;
  text-align: center;
  cursor: pointer;
}
.search-box {
  flex: 0 0 300px;
  width: 300px;
  text-align: left;
  position: relative;
  margin-top: 10px;
}
.search-box input {
  height: 40px;
  width: 180px;
  outline: none;
  padding: 0 16px;
  border-radius: 20px;
  border: solid 1px #409eff;
  position: absolute;
  top: 18px;
  left: 0;
}
.icon {
  color: #409eff;
  font-size: 20px;
  vertical-align: middle;
  position: absolute;
  top: 30px;
  left: 180px;
  cursor: pointer;
}
</style>


