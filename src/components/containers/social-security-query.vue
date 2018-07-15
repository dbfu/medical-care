<template>
  <div class="container">
    <Header></Header>
    <div class="nav-info">
      <span>常见服务 |
        <span style="color: #2873C8;">社保政策查询</span>
      </span>
    </div>
    <div class="tabel-box">
      <div class="table-header">
        <el-form :inline="true" :model="formInline" class="demo-form-inline">
          <el-form-item label="缴费城市">
            <el-select v-model="cityId">
              <el-option v-for="item in city" :key="item.id" :label="item.name" :value="item.id"></el-option>
            </el-select>
          </el-form-item>
          <el-form-item label="缴费基数">
            <el-input v-model="minCardinality"></el-input>
          </el-form-item>
          <el-form-item label="最低缴费基数">
            <span style="color: #2873C8;">500元</span>
          </el-form-item>
          <span style="margin: 0 40px;"></span>
          <el-form-item>
            <el-button round type="primary" size="middle" @click="onSubmit">查询</el-button>
          </el-form-item>
        </el-form>
        <div style="margin-top: 10px;"></div>
        <el-table border stripe :data="data">
          <el-table-column width="300" align="center" label="保险类型" prop="type">
            <span class="column" slot-scope="model">{{model.row.type}}</span>
          </el-table-column>
          <el-table-column align="center" label="个人" prop="person"></el-table-column>
          <el-table-column align="center" label="公司" prop="company"></el-table-column>
        </el-table>
        <div class="table-footer">
          <span>缴纳总额：<span style="color: green;">{{totallAmount}}</span> 个人缴纳: <span style="color: green;">{{personTotallAmount}}</span> 单位缴纳: <span style="color: green;">{{companyTotallAmount}}</span></span>
        </div>
      </div>
    </div>
    <div class="tab-box">
      <div class="tab-title">
        <span>城市社保咨询</span>
      </div>
      <ul class="tab-container">
        <li @click="index=1" :class="{selected: index===1}">医疗</li>
        <li @click="index=2" :class="{selected: index===2}">生育</li>
        <li @click="index=3" :class="{selected: index===3}">养老</li>
        <li @click="index=4" :class="{selected: index===4}">工伤</li>
        <li @click="index=5" :class="{selected: index===5}">失业</li>
      </ul>
      <div class="tab-content">
        <MessageItem></MessageItem>
        <MessageItem></MessageItem>
        <MessageItem></MessageItem>
        <MessageItem></MessageItem>
        <MessageItem></MessageItem>
      </div>
      <div class="pagination-box">
        <el-pagination background layout="prev, pager, next" :total="1000">
        </el-pagination>
      </div>
    </div>
    <div class="tab-box">
      <div class="tab-title">
        <span>热门商业保险</span>
      </div>
      <el-row style="padding: 20px 30px;" :gutter="40">
        <el-col :span="8">
          <HealthCard color="#479DFE"></HealthCard>
        </el-col>
        <el-col :span="8">
          <HealthCard color="#DBB17E"></HealthCard>
        </el-col>
        <el-col :span="8">
          <HealthCard color="#46F072"></HealthCard>
        </el-col>
      </el-row>
    </div>
  </div>
</template>
<script>
import Header from "../common/header";
import MessageItem from "../common/message-item";
import HealthCard from "../common/health-card";
export default {
  components: {
    Header,
    MessageItem,
    HealthCard
  },
  data() {
    return {
      data: [],
      index: 1,
      city: [],
      cityId: "",
      minCardinality: 500,
      types: ["养老保险", "医疗", "失业", "工伤", "生育"],
      totallAmount: 0,
      personTotallAmount: 0,
      companyTotallAmount: 0
    };
  },
  mounted() {
    this.$axios.get("/api/socialInsurancePolicy/allcitys").then(res => {
      this.city = res.data;
    });
  },
  methods: {
    getList() {
      this.$axios
        .get(
          `/api/socialInsurancePolicy/socialInsurancePolicyVo/${
            this.minCardinality
          }/${this.cityId}`
        )
        .then(res => {
          let list = res.data.list || [];

          list.map(item => {
            item.type = this.types[item.type - 1];
            item.person =
              Number(item.personAmount).toFixed(2) +
              `(${item.personRate || 0}%)`;
            item.company =
              Number(item.companyAmount).toFixed(2) +
              `(${item.companyRate || 0}%)`;
          });

          this.totallAmount = Number(res.data.totallAmount || 0).toFixed(2);
          this.personTotallAmount = Number(
            res.data.personTotallAmount || 0
          ).toFixed(2);
          this.companyTotallAmount = Number(
            res.data.companyTotallAmount || 0
          ).toFixed(2);

          this.data = list;
        });
    },
    onSubmit() {
      this.getList();
    }
  }
};
</script>
<style scoped>
.container {
  background: #efefef;
  padding-bottom: 40px;
}
.nav-info {
  padding: 0 70px;
  height: 86px;
  line-height: 86px;
  font-size: 22px;
  color: #666;
}
.tabel-box {
  background-color: #fff;
  margin: 0px 70px;
  padding: 40px 20px;
}
.table-footer {
  line-height: 60px;
  text-align: right;
  font-size: 16px;
  color: #333333;
}
.tab-box {
  margin: 20px 70px;
  background-color: #fff;
  padding: 0px 00px;
}
.tab-title {
  height: 60px;
  line-height: 60px;
  color: #333333;
  font-size: 22px;
  padding: 0 30px;
}
.tab-container {
  border-bottom: 1px solid #e5e5e5;
  border-top: 1px solid #e5e5e5;
  line-height: 60px;
  height: 60px;
  list-style: none;
  display: flex;
}
.tab-container li {
  height: 60px;
  line-height: 60px;
  color: #333333;
  flex: 0 0 200px;
  text-align: center;
  cursor: pointer;
}
.tab-container li.selected {
  color: #2873c8;
  border-bottom: 6px solid #2873c8;
}
.pagination-box {
  text-align: center;
  padding: 20px 0;
}
.column {
  color: #333;
  font-size: 16px;
}
</style>
