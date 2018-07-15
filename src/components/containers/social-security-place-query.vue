<template>
  <div class="container">
    <Header></Header>
    <div class="nav-info">
      <span>常见服务 |
        <span style="color: #2873C8;">社保网点查询</span>
      </span>
    </div>
    <div class="tabel-box">
      <div class="table-header">
        <el-form :inline="true"  class="demo-form-inline">
          <el-form-item label="所在城市">
            <el-select v-model="selectCity" @change='chanegCity'> 
              <el-option 
              v-for="item in citys"
              :key="item.id"
              :label="item.name"
              :value="item.id"
              ></el-option>
            </el-select>
          </el-form-item>
          <el-form-item label="所在区域">
            <el-select v-model='selectArea'>
              <el-option
              v-for="item in areas"
              :key="item.id"
              :label="item.name"
              :value="item.id"></el-option>
          
            </el-select>
          </el-form-item>
          <el-form-item label="类型">
            <el-select v-model='type'>
              <el-option v-for="item in types"
                :key="item.id"
                :label="item.name"
                :value="item.id"
              ></el-option>
            </el-select>
          </el-form-item>
          <span style="margin: 0 40px;"></span>
          <el-form-item>
            <el-button round type="primary" size="middle" @click="onSubmit">查询</el-button>
          </el-form-item>
        </el-form>
        <div style="margin-top: 10px;"></div>
        <div class="result-box" v-for="item in infos" :key='item.id'>
          <PlaceCard :datas="item"></PlaceCard>
    
        </div>
          <div class="pagination">
            <el-pagination
            @current-change="handleCurrentChange"
            :page-sizes="[10, 20, 30, 40]"
            :page-size="10"
            layout=" prev, pager,next,sizes,total"
              background
              :total="totalElements">
            </el-pagination>
          </div>
      </div>
    </div>
  </div>
</template>
<script>
import Header from "../common/header";
import MessageItem from "../common/message-item";
import HealthCard from "../common/health-card";
import PlaceCard from "../common/place-item";
export default {
  components: {
    Header,
    MessageItem,
    HealthCard,
    PlaceCard
  },
  data() {
    return {
      types:[{
        id:0,
        name:'医院'
      },{
        id:1,
        name:'药房'
      }],
      index: 1,
      infos:[],
      citys:[],
      areas:[],
      selectCity:'',
      selectArea:'',
      type:'',
      page:0,
      totalElements:null,
      newHotDrugs:'',
      initParams : {
            page:0,
            addressId:null,
            type:null
          }
    }
  },
  mounted(){
    this.getAllList();
    this.getCitys({parentId:0});
    // this.getHotDrug();
  },
  methods:{
      getCitys(params){
          this.$axios.get(`http://47.104.99.233:8083/socialInsuranceAgency/getAddress/${params.parentId}`).then(res => {
            if(params.parentId==0){
               this.citys = res.data;
            }else{
              this.areas = res.data;
            }
         
        })
      },
      getAllList(){
          const initParams = this.initParams;
          this.$axios.get(`http://47.104.99.233:8083/socialInsuranceAgency/getAll/${initParams.page}/${initParams.addressId}/${initParams.type}`,{params:initParams})
          .then(res => {
               this.infos = res.data.content;
               this.totalElements = res.data.totalElements;
            })
        },
        chanegCity(v){
          this.selectArea='';
          this.getCitys({parentId:v})
        },
        onSubmit(){
          let initParams = this.initParams;
          initParams.page=this.page;
          initParams.addressId=this.selectArea;
          initParams.type=this.type;
          this.getAllList();
        },
        handleCurrentChange(val){  
          const page = val-1;
          let initParams = this.initParams;
          initParams.page=page;
          initParams.addressId=this.selectArea || null;
          initParams.type=this.type || null;
          this.getAllList();
      },
      // getHotDrug(){
      //     const medicines = this.infos.medicines;
      //     let hotDrugs = [];
      //     medicines.map(item=>{
      //       hotDrugs.push(item.medicineName.genericName);
      //     })
      //     this.newHotDrugs = hotDrugs.join('|');
      //     this.newHotDrugs = this.newHotDrugs.subString(0,newHotDrugs.Length-1);
      // }
  },

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
  padding: 40px 40px;
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
.pagination{
  margin-top: calc(10/1080*100vh);
 /*  margin-left: 50%;
  transform: translate(-50%); */
  float: right;
}
</style>
