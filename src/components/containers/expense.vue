<template>
  <div>
    <Header>hello</Header>
   <div class="content" >
      <div class="capacity-title">
        <a href="#">常见服务</a> | <a class="active" href="#">报销药品查询</a> 
      </div>
      <div class="expense">
        <div class="expense-form">
          <el-form :inline="true"  class="demo-form-inline">
              <el-form-item label="报销城市">
                <el-select v-model="value2"  placeholder="请选择报销城市">
                  <el-option  v-for="item in citys"
                   :key="item.id"
                   :label="item.name"
                   :value="item.id"></el-option>
                </el-select>
              </el-form-item>
              <el-form-item label="药品名称">
                <el-input v-model="drugName" placeholder="请输入药品名称，如 白加黑"></el-input>
              </el-form-item>
              
              <el-form-item>
                <el-button type="primary" @click="onSubmit">查询</el-button>
              </el-form-item>
          </el-form>
        </div>
        <div class="clearfix">
          <el-table
            stripe
            :data="medicines"
            border
            style="width: 100%">
            <el-table-column
              prop="drugType"
              label="药品类型"
              align='center'
              min-width='25%'>
            </el-table-column>
            <el-table-column
              prop="medicineName.genericName"
              label="药品名称"
              align='center'
              min-width='25%'>
            </el-table-column>
            <el-table-column
              prop="drugDosage"
              label="药品剂型"
              align='center'
              min-width='25%'>
            </el-table-column>
            <el-table-column
              prop="drugNo"
              label="药品编号"
              align='center'
              min-width='25%'>
            </el-table-column>
          </el-table>
          
          </div>
          <div class="pagination">
            <el-pagination
            @size-change="handleSizeChange"
            @current-change="handleCurrentChange"
            :page-sizes="[10, 20, 30, 40]"
            :page-size="10"
            layout=" prev, pager,next,sizes,total"
              background
              :total="totalElements">
            </el-pagination>
          </div>

          <div class="card-box">
          <div class="capacity-title">
            <a style="margin-left:calc(30/1920*100vw)" class='hot-pic' href="#">类似药品</a>
          </div>
          <el-row style="padding-left:calc(100/1920*100vw)">
              <el-col :offset="1" :span="8" class='hot-box'><div class="grid-content bg-purple">
                <img  src="../../assets/images/00012.jpeg"/>
                <span>上海市长江医院</span>
                <i>推荐</i>
              </div></el-col>
              <el-col :offset="1" :span="8" class='hot-box'><div class="grid-content bg-purple-light">
                <img  src="../../assets/images/00013.jpeg"/>
                 <span>上海市新华医院（祟明）</span>
                 <i>可报销</i>
              </div></el-col>
              <el-col :offset="1" :span="8" class='hot-box'><div class="grid-content bg-purple">
                <img  src="../../assets/images/00010.jpeg"/>
                 <span>上海市新华医院（祟明）</span>
              </div></el-col>
            </el-row>
        </div>
      </div>
   </div>
    <Footer></Footer>
  </div>
</template>
<script>
import Header from "../common/header";
import Card from "../common/card";
import Search from "../common/search";
import Footer from "../common//footer";
export default {
  components: {
    Header,
    Card,
    Search,
    Footer
  },
  data() {
    return {
      currentTab: 1,
      currentIndex: 2,
      citys:[],
      value2:'',
      medicines:[],
      totalElements:null,
      drugName:'',
      page:0
    };
  },
  methods:{
    getCitys(){
        this.$axios.get("/api/socialInsurancePolicy/allcitys").then(res => {
        this.citys = res.data;
      })
    },
    getAllMedicine(params){
      this.$axios.get(`/api/medicine/getReimburseMedicine`,{params}).then(res => {
       this.medicines = res.data.content;
       this.totalElements = res.data.totalElements;
      })
    },
    handleSizeChange(){

    },
    handleCurrentChange(val){  
      this.page = val-1;
       this.getAllMedicine({ page:val-1});
    },
    onSubmit(){ 
      console.log(this.page)
      this.page = 0;
        this.$axios.get(`/api/medicine/getReimburseMedicine`,{
          params:{
            cityId:this.value2,
            medicineName:this.drugName,
            page:this.page
          }
        }).then(res => {
        this.medicines = res.data.content;
        this.totalElements = res.data.totalElements;
      })
    }
  },
  created(){
  }
  ,
  mounted() {
   this.getCitys();
   this.getAllMedicine({
        page:0
      });
  },
};
</script>
<style>
.el-table th{
  background-color: #C9DBEE;
}
.content{
  background-color: #efefef;
}
.capacity-title{
  margin: calc(20/1080*100vh) 0;
}
.expense{
  padding: calc(40/1080*100vh) calc(30/1920*100vw);
 background-color: #fff;
}
.pagination{
  margin-top: calc(50/1080*100vh);
  margin-left: 50%;
  transform: translate(-50%);
}
</style>

