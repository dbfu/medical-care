<template>
  <div>
    <Header :userName="logined?user:''"></Header>
    <el-carousel style="padding: 0 70px;" height="550px">
      <el-carousel-item v-for="item in 4" :key="item">
        <img src="../../assets/images/luobo.png">
      </el-carousel-item>
    </el-carousel>
    <div v-if="!logined" class="login-box">
      <div style="border-top-left-radius: 4px;border-top-right-radius: 4px;line-height: 48px; text-align: center; background-color: #479dfe;color: #fff;">用户登录</div>
      <div style="padding: 28px 20px;">
        <el-input v-model="user" placeholder="请输入用户名">
          <i slot="prefix" class="el-input__icon el-icon-mobile-phone"></i>
        </el-input>
        <div style="margin: 20px 0;"></div>
        <el-input v-model="pass" auto-complete="off" type="password" placeholder="请输入密码">
          <i slot="prefix" class="el-input__icon el-icon-goods"></i>
        </el-input>
        <el-button @click="login" style="width: 100%; margin: 0 auto; margin-top:60px;" type="primary">登录</el-button>
      </div>
    </div>
    <Card title="常用服务">
      <el-row slot="content">
        <el-col :span="4">
          <div @click="() => skip('/capacity')" class="service-box">
            <img slot="content" src="../../assets/images/medical-history (1)@2x.png" />
            <div>智能自诊</div>
          </div>
        </el-col>
        <el-col :offset="1" :span="4">
          <div @click="() => skip('/social-security-query')" class="service-box">
            <img slot="content" src="../../assets/images/hospital@2x.png" />
            <div>社保政策查询</div>
          </div>
        </el-col>
        <el-col :offset="1" :span="4">
          <div @click="() => skip('/expense')" class="service-box">
            <img slot="content" src="../../assets/images/pills-1@2x.png" />
            <div>药品报销查询</div>
          </div>
        </el-col>
        <el-col :offset="1" :span="4">
          <div @click="() => skip('/social-security-place-query')" class="service-box">
            <img slot="content" src="../../assets/images/medical-history (1)@2x.png" />
            <div>社保网点咨询</div>
          </div>
        </el-col>
        <el-col :offset="1" :span="4">
          <div class="service-box">
            <img slot="content" src="../../assets/images/medical-history (1)@2x.png" />
            <div>其他</div>
          </div>
        </el-col>
      </el-row>
    </Card>
    <Card title="智能自诊">
      <el-row slot="content">
        <el-col :span="4">
          <div class="illness-box">
            <img class="text-bg" src="../../assets/images/rectangle.png">
            <span class="illness-name">高血压</span>
            <img style="width: 100%;height: 150px;" src="../../assets/images/0000.jpg" />
          </div>
        </el-col>
        <el-col :offset="1" :span="4">
          <div class="illness-box">
            <img class="text-bg" src="../../assets/images/rectangle.png">
            <span class="illness-name">流行感冒</span>
            <img style="width: 100%;height: 150px;" src="../../assets/images/0001.jpg" />
          </div>
        </el-col>
        <el-col :offset="1" :span="4">
          <div class="illness-box">
            <img class="text-bg" src="../../assets/images/rectangle.png">
            <span class="illness-name">减肥瘦身</span>
            <img style="width: 100%;height: 150px;" src="../../assets/images/0002.jpg" />
          </div>
        </el-col>
        <el-col :offset="1" :span="4">
          <div class="illness-box">
            <img class="text-bg" src="../../assets/images/rectangle.png">
            <span class="illness-name">高血压</span>
            <img style="width: 100%;height: 150px;" src="../../assets/images/0000.jpg" />
          </div>
        </el-col>
        <el-col :offset="1" :span="4">
          <div class="illness-box">
            <img class="text-bg" src="../../assets/images/rectangle.png">
            <span class="illness-name">流行感冒</span>
            <img style="width: 100%;height: 150px;" src="../../assets/images/0001.jpg" />
          </div>
        </el-col>
      </el-row>
      <el-row style="margin-top: 16px;" slot="content">
        <el-col :span="4">
          <div class="illness-box">
            <img class="text-bg" src="../../assets/images/rectangle.png">
            <span class="illness-name">高血压</span>
            <img style="width: 100%;height: 150px;" src="../../assets/images/0000.jpg" />
          </div>
        </el-col>
        <el-col :offset="1" :span="4">
          <div class="illness-box">
            <img class="text-bg" src="../../assets/images/rectangle.png">
            <span class="illness-name">流行感冒</span>
            <img style="width: 100%;height: 150px;" src="../../assets/images/0001.jpg" />
          </div>
        </el-col>
        <el-col :offset="1" :span="4">
          <div class="illness-box">
            <img class="text-bg" src="../../assets/images/rectangle.png">
            <span class="illness-name">减肥瘦身</span>
            <img style="width: 100%;height: 150px;" src="../../assets/images/0002.jpg" />
          </div>
        </el-col>
        <el-col :offset="1" :span="4">
          <div class="illness-box">
            <img class="text-bg" src="../../assets/images/rectangle.png">
            <span class="illness-name">高血压</span>
            <img style="width: 100%;height: 150px;" src="../../assets/images/0000.jpg" />
          </div>
        </el-col>
        <el-col :offset="1" :span="4">
          <div class="illness-box">
            <img class="text-bg" src="../../assets/images/rectangle.png">
            <span class="illness-name">流行感冒</span>
            <img style="width: 100%;height: 150px;" src="../../assets/images/0001.jpg" />
          </div>
        </el-col>
      </el-row>
    </Card>
    <Card title="药品商城">
      <div slot="content">
        <div class="title-box">
          <div class="left-box">
            <span class="content-title">适用症状</span>
            <ul class="content-nav">
              <li @click="select(item)" v-for="item in categorys" :class="{selected:selected.id == item.id}" :key="item.id">{{item.indicationName}}</li>
            </ul>
          </div>
          <div class="content-search-box">
            <Search></Search>
          </div>
        </div>
        <div class="drug-list">
          <el-row :gutter="20">
            <el-col v-for="item in medicines" :key="item.id" :span="6">
              <DrugCard :drugInfo='item'></DrugCard>
            </el-col>
          </el-row>
        </div>
      </div>
    </Card>
    <Card title="健康商城">
      <div slot="content" class="drug-list">
        <el-row :gutter="20">
          <el-col :span="8">
            <div @click="currentIndex=1" class="healthy-box">
              <img :class="{selected: currentIndex===1 }" src="../../assets/images/0000.jpg" />
              <div class="healthy-desc">
                <span style="font-size: 26px;color: #fff;">健康体检卡B 基础套餐</span>
              </div>
            </div>
          </el-col>
          <el-col :span="8">
            <div @click="currentIndex=2" class="healthy-box">
              <img :class="{selected: currentIndex===2 }" src="../../assets/images/0000.jpg" />
              <div class="healthy-desc" style="background-color: #479DFE ">
                <span style="font-size: 26px;color: #fff;">健康体检卡A 基础套餐</span>
              </div>
            </div>
          </el-col>
          <el-col :span="8">
            <div @click="currentIndex=3" class="healthy-box">
              <img :class="{selected: currentIndex===3 }" src="../../assets/images/0000.jpg" />
              <div class="healthy-desc" style="background-color: #F0AB46">
                <span style="font-size: 26px;color: #fff;">健康体检卡B 基础套餐</span>
              </div>
            </div>
          </el-col>
        </el-row>
      </div>
    </Card>
    <Card title="医疗服务">
      <div slot="content" class="medical">
        <div class="medical-left-box">
          <ul class="medical-tab-box">
            <li @click="selectHot(1)" :class="{selected: currentTab === 1 }">热门医院</li>
            <li @click="selectHot(2)" :class="{selected: currentTab === 2 }">热门医生</li>
            <li @click="selectHot(3)" :class="{selected: currentTab === 3 }">热门咨询</li>
          </ul>
        </div>
        <div class="medical-right-box">
          <el-row :gutter="20">
            <el-col v-for="item in hospitals" :key="item.id" style="text-align: center;" :span="6">
              <img style="height: 220px; width: 100%;margin-bottom: 10px;" :src="item.imageUrl" />
              <span style="color: #333;">{{item.name}}</span>
            </el-col>
            <el-col style="text-align: center;" :span="6">
              <div class="more-button">查看更多</div>
            </el-col>
          </el-row>
        </div>
      </div>
    </Card>
    <Footer></Footer>
  </div>
</template>
<script>
import Header from "../common/header";
import Card from "../common/card";
import Search from "../common/search";
import DrugCard from "../common/drug-card";
import Footer from "../common//footer";
export default {
  components: {
    Header,
    Card,
    Search,
    DrugCard,
    Footer
  },
  data() {
    return {
      currentTab: 1,
      currentIndex: 2,
      user: "",
      pass: "",
      logined: false,
      categorys: [],
      selected: {},
      medicines: [],
      hospitals: []
    };
  },
  mounted() {
    this.$axios.get("api/hospital/getAll/0").then(res => {
      console.log(res.data);
    });
    this.$axios.get("api/indication/getAll/0").then(res => {
      this.categorys = res.data.content.slice(0, 4);
      this.selected = this.categorys[0];

      this.$axios
        .get(`/api/medicine/getByIndication/${this.selected.id}/0`)
        .then(res => {
          this.medicines = res.data.content.splice(0, 4);
        });
    });
    this.$axios.get("api/hospital/getHot/0").then(res => {
      res.data.content.map(item => {
        item.imageUrl = `http://${item.fileServerIp}:${item.fileServerPort}${
          item.fileServerPath
        }${item.imgUrl}`;
      });

      this.hospitals = res.data.content;
    });

    this.$axios.get("api/hospital/getHot/0").then(res => {
      res.data.map(item => {
        item.imageUrl = `http://${item.fileServerIp}:${item.fileServerPort}${
          item.fileServerPath
        }${item.imageUrl}`;
      });

      this.hospitals = res.data.splice(0, 3);
    });
  },
  methods: {
    skip(path) {
      this.$router.push({ path });
    },
    login() {
      this.$axios
        .post("api/user/login", { name: this.user, password: this.pass })
        .then(res => {
          if (!res.data) {
            this.$message.error("账户或用户名错误！");
          } else {
            this.logined = true;
            this.$message.success("hello " + this.user);
          }
        });
    },
    select(item) {
      this.$axios
        .get(`/api/medicine/getByIndication/${item.id}/0`)
        .then(res => {
          this.medicines = res.data.content.splice(0, 4);
        });
      this.selected = item;
    },
    selectHot(index) {
      if (index === this.currentTab) return;
      this.currentTab = index;
      if (index === 1) {
        this.$axios.get("api/hospital/getHot/0").then(res => {
          res.data.map(item => {
            item.imageUrl = `http://${item.fileServerIp}:${
              item.fileServerPort
            }${item.fileServerPath}${item.imageUrl}`;
          });

          this.hospitals = res.data.splice(0, 3);
        });
      }
      if (index === 2) {
        this.$axios.get("api/doctor/getHot/0").then(res => {
          res.data.map(item => {
            item.imageUrl = `http://${item.fileServerIp}:${
              item.fileServerPort
            }${item.fileServerPath}${item.imgUrl}`;
          });

          this.hospitals = res.data.splice(0, 3);
        });
      }
      if (index === 3) {
        this.$axios.get("api/information/getHot?hotFlag=Y&page=0").then(res => {
          res.data.map(item => {
            item.imageUrl = `http://${item.fileServerIp}:${
              item.fileServerPort
            }${item.fileServerPath}${item.imgUrl}`;
          });

          this.hospitals = res.data.splice(0, 3);
        });
      }
    }
  }
};
</script>
<style scoped>
.el-carousel__item img {
  width: 100%;
}

.title-box {
  display: flex;
  height: 60px;
  line-height: 60px;
  justify-content: space-between;
}
.left-box {
  display: flex;
  flex: 1;
}
.content-title {
  width: 120px;
  flex: 0 0 120px;
  vertical-align: middle;
}
.content-nav {
  list-style: none;
  flex: 0 0 400px;
  width: 400px;
  display: flex;
  vertical-align: middle;
  cursor: pointer;
}
.content-nav li {
  flex: 1;
  text-align: center;
  cursor: pointer;
}

.content-nav li.selected {
  color: #538fd3;
}

.content-search-box {
  flex: 0 0 274px;
  text-align: right;
  margin-top: 10px;
}

.service-content {
  width: 100%;
}

.service-box {
  background-color: #fff;
  text-align: center;
  padding: 24px 0;
  box-shadow: 0px 1px 20px #ccc;
  cursor: pointer;
}
.service-box img {
  width: 82px;
  height: 86px;
}
.service-box div {
  margin-top: 28px;
}
.illness-box {
  position: relative;
}
.text-bg {
  position: absolute;
  width: 80px;
  right: 0;
  height: 22px;
}
.illness-name {
  display: block;
  position: absolute;
  text-align: center;
  color: #fff;
  right: 0;
  font-size: 12px;
  width: 80px;
  line-height: 22px;
}
.healthy-box {
  position: relative;
  cursor: pointer;
}
.healthy-box img.selected {
  height: 290px;
}
.healthy-box img {
  width: 100%;
  height: 270px;
  border-top-left-radius: 8px;
  border-top-right-radius: 8px;
}
.healthy-desc {
  position: absolute;
  left: 0;
  right: 0;
  bottom: 0;
  height: 74px;
  background-color: #13ba8e;
  line-height: 74px;
  text-align: center;
  border-bottom-left-radius: 8px;
  border-bottom-right-radius: 8px;
}
.medical {
  display: flex;
  background: #f7fbff;
}
.medical-left-box {
  flex: 0 0 200px;
  width: 200px;
}
.medical-tab-box {
  list-style: none;
}
.medical-tab-box li {
  text-align: center;
  height: 100px;
  line-height: 100px;
  font-size: 20px;
  color: #333;
  border: 1px solid #e5e5e5;
  border-top: 0;
  background-color: #fff;
  cursor: pointer;
}
.medical-tab-box li.selected {
  color: #479dfe;
  border-left: 0;
  border-right: 0;
  background: #f7fbff;
}
.medical-right-box {
  padding: 20px 40px;
  flex: 1;
}
.more-button {
  background-color: #479dfe;
  line-height: 46px;
  width: 60%;
  margin: 88px auto;
  border-radius: 35px;
  color: #fff;
  cursor: pointer;
  font-size: 20px;
}
.login-box {
  position: absolute;
  top: 240px;
  right: 160px;
  width: 300px;
  z-index: 9999;
  background-color: #fff;
  border-radius: 4px;
}
</style>

