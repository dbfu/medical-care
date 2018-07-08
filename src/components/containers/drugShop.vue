<template>
  <div>
    <Header1>hello</Header1>
    <div class="content" style="padding:0">
      <div class="clearfix" style="padding:calc(30/1080*100vh) 0 0 calc(260/1080*100vh)">
        <div class="logo fl">
          <img src="../../assets/images/logo.png" class="logo" />
          <a href="#">药品商城</a>
        </div>
        <div class="fl logo_r">
          <div class="search">
            <input type="text" placeholder="请输入药品名称，如 白加黑" />
            <button>搜索</button>
          </div>
          <div class="hotwords">
            <span>常见状态：</span>
            <a href="#">冠心病</a>
            <a href="#">感冒</a>
            <a href="#">发烧</a>
            <a href="#">头晕</a>
            <a href="#">眼干</a>
            <a href="#">鼻炎</a>
          </div>
        </div>
      </div>

    </div>
    <div class="nav-box">
      <ul class="nav">
        <li>首页</li>
        <li>新人专区</li>
        <li>新特效</li>
        <li>送礼送健康</li>
        <li>男性健康</li>
        <li>全球购</li>
        <li>一小时购药</li>
        <li>网络医院</li>
      </ul>
    </div>
    <div class="banner w">
      <el-carousel height="calc(550/1080*100vh)">
        <el-carousel-item v-for="item in 4" :key="item">
          <img width="100%" height="100%" src="../../assets/images/00026.png">
        </el-carousel-item>
      </el-carousel>
      <div class='allShops'>
        <h3>全部商品分类</h3>
        <ul>
          <li v-for="item in categorys">
            <label>{{item.categoryName}}</label>
            <span>血压计 / 茅台药酒</span>
          </li>
        </ul>
      </div>
      </Card>
      <Card title="热卖专区">
        <div slot="content">
          <div class="drug-list">
            <el-row :gutter="20">
              <el-col :span="6" v-for="item in hotFlag" >
                <div>
                  <DrugCard  :drugInfo='item'></DrugCard>
                </div>
                
              </el-col>
            </el-row>
            <div class="pagination">
                <el-pagination
                @current-change="handleCurrentChange"
                :page-sizes="[8, 16, 24, 32]"
                :page-size="8"
                layout=" prev, pager,next,sizes,total"
                  background
                  :total="totalElements">
                </el-pagination>
            </div>
          </div>
        </div>
      </Card>
    </div>
    <Footer> </Footer>
  </div>
</template>
<script>
import Header1 from "../common/header1";
import Card from "../common/card";
import Search from "../common/search";
import Footer from "../common//footer";
import DrugCard from "../common/drug-card";
export default {
  components: {
    Header1,
    Card,
    Search,
    DrugCard,
    Footer
  },
  data() {
    return {
      currentTab: 1,
      currentIndex: 2,
      categorys:[],
      hotFlag:[],
      totalElements:null
    };
  },
  methods:{ 
      getCategory(){
          const page = 0;
          this.$axios.get(`/api/category/getAll/${page}`).then(res => {
            this.categorys = res.data.content;
        })
      },
      getMedicineByHotFlag(params){
        this.$axios.get(`/api/medicine/getMedicineByHotFlag`,{params:params}).then(res => {
            this.hotFlag = res.data.content;
             this.totalElements = res.data.totalElements;
            console.log(this.hotFlag)
        })
      },
      handleCurrentChange(val){
        const page = val-1;
        const params = {
          hotFlag:'Y',
          page,
          size:8
        }
        this.getMedicineByHotFlag(params);
      },
  },
  mounted(){
      this.getCategory();
      const initParams = {
        hotFlag:'Y',
        page:0,
        size:8
      }
      this.getMedicineByHotFlag(initParams);
  }
};
</script>
<style scoped>
.content {
  background-color: #fff;
}
.logo {
  vertical-align: middle;
}
.logo a {
  font-family: PingFangSC-Regular;
  color: #3271c0;
}
.logo_r {
  margin-left:calc(153/1920*100vw);
}
.search {
  position: relative;
}
.search input {
  width: calc(809/1920*100vw);
  height: calc(47/1080*100vh);
  outline: none;
  border: calc(3/1080*100vh) solid #fa344d;
  border-radius: calc(30/1920*100vw);
  font-size: calc(22/1920*100vw);
  text-indent: 2em;
}
.search button {
  width: calc(99/1920*100vw);
  height: calc(47/1080*100vh);
  background: #fa344d;
  border-radius: calc(34/1080*100vh);
  color: #fff;
  font-size: calc(22/1080*100vh);
  outline-style: none;
  list-style-type: none;
  border: none;
  position: absolute;
  top: calc(3/1080*100vh);
  right: calc(2/1920*100vw);
}
.hotwords {
  margin-top: calc(6/1080*100vh);
  margin-left: 2em;
  color: #999;
}
.hotwords a {
  color: #999;
}
.nav-box {
  height: calc(47/1080*100vh);
  background: #fa344d;
  line-height: calc(47/1080*100vh);
  width: 100%;
  margin-top: calc(30/1080*100vh);
}
.nav {
  margin-left: calc(650/1920*100vw);
}
.nav li {
  float: left;
  font-size: calc(22/1080*100vh);
  text-align: center;
  cursor: pointer;
  margin-right: calc(30/1920*100vw);
  color: #fff;
}
.banner {
  position: relative;
}
.allShops {
  width: calc(309/1920*100vw);
  opacity: 0.7;
  background: #05314a;
  position: absolute;
  top: calc(-47/1080*100vh);
  left: 0;
  z-index: 99999;
}
.allShops h3 {
  background: #cd0f25;
  width: calc(309/1920*100vw);
  height: calc(47/1080*100vh);
  line-height: calc(47/1080*100vh);
  text-align: center;
  color: #fff;
  font-weight: 700;
}
.allShops ul {
  padding: calc(10/1080*100vh) 0 0 calc(45/1080*100vh);
}
.allShops ul li {
  height: calc(60/1080*100vh);
}
.allShops ul li label {
  display: inline-block;
  width: calc(80/1920*100vw);
  font-size: calc(20/1920*100vw);
  color: #fff;
  margin-right: calc(15/1920*100vw);
}
.allShops ul li span {
  font-size: calc(16/1920*100vw);
  color: #fff;
  cursor: pointer;
}
.contanier[data-v-39d49e21] {
  padding: 0 !important;
}
</style>

