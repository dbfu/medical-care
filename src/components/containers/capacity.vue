<template>
  <div class="box">
    <Header>hello</Header>
    <div class="content" >
      <div class="capacity-title">
        <a href="#">常见服务</a> | <a class="active" href="#">智能自诊</a> 
      </div>
      <el-row slot="content">
        <el-col :span="4">
          <div class="illness-box">
            <img class="text-bg" src="../../assets/images/rectangle.png">
            <span class="illness-name">高血压</span>
            <img style="width: 100%;height:calc(150/1080*100vh);" src="../../assets/images/0000.jpg" />
          </div>
        </el-col>
        <el-col :offset="1" :span="4">
          <div class="illness-box">
            <img class="text-bg" src="../../assets/images/rectangle.png">
            <span class="illness-name">流行感冒</span>
            <img style="width: 100%;height: calc(150/1080*100vh);" src="../../assets/images/0001.jpg" />
          </div>
        </el-col>
        <el-col :offset="1" :span="4">
          <div class="illness-box">
            <img class="text-bg" src="../../assets/images/rectangle.png">
            <span class="illness-name">减肥瘦身</span>
            <img style="width: 100%;height: calc(150/1080*100vh);" src="../../assets/images/0002.jpg" />
          </div>
        </el-col>
        <el-col :offset="1" :span="4">
          <div class="illness-box">
            <img class="text-bg" src="../../assets/images/rectangle.png">
            <span class="illness-name">高血压</span>
            <img style="width: 100%;height: calc(150/1080*100vh);" src="../../assets/images/0000.jpg" />
          </div>
        </el-col>
        <el-col :offset="1" :span="4">
          <div class="illness-box">
            <img class="text-bg" src="../../assets/images/rectangle.png">
            <span class="illness-name">流行感冒</span>
            <img style="width: 100%;height: calc(150/1080*100vh)x;" src="../../assets/images/0001.jpg" />
          </div>
        </el-col>
      </el-row>
      <el-row style="margin-top: calc(16/1080*100vh);" slot="content">
        <el-col :span="4">
          <div class="illness-box">
            <img class="text-bg" src="../../assets/images/rectangle.png">
            <span class="illness-name">高血压</span>
            <img style="width: 100%;height: calc(150/1080*100vh);" src="../../assets/images/0000.jpg" />
          </div>
        </el-col>
        <el-col :offset="1" :span="4">
          <div class="illness-box">
            <img class="text-bg" src="../../assets/images/rectangle.png">
            <span class="illness-name">流行感冒</span>
            <img style="width: 100%;height: calc(150/1080*100vh);" src="../../assets/images/0001.jpg" />
          </div>
        </el-col>
        <el-col :offset="1" :span="4">
          <div class="illness-box">
            <img class="text-bg" src="../../assets/images/rectangle.png">
            <span class="illness-name">减肥瘦身</span>
            <img style="width: 100%;height: calc(150/1080*100vh);" src="../../assets/images/0002.jpg" />
          </div>
        </el-col>
        <el-col :offset="1" :span="4">
          <div class="illness-box">
            <img class="text-bg" src="../../assets/images/rectangle.png">
            <span class="illness-name">高血压</span>
            <img style="width: 100%;height: calc(150/1080*100vh);" src="../../assets/images/0000.jpg" />
          </div>
        </el-col>
        <el-col :offset="1" :span="4">
          <div class="illness-box">
            <img class="text-bg" src="../../assets/images/rectangle.png">
            <span class="illness-name">流行感冒</span>
            <img style="width: 100%;height: calc(150/1080*100vh);" src="../../assets/images/0001.jpg" />
          </div>
        </el-col>
      </el-row>

    <div class="symptom clearfix" style="background: #fff;margin-top:calc(10/1080*100vh)">
      <div class="symptom_l fl">
        <p>主要症状</p>
        <p>伴随症状</p>
        <p>相关信息</p>
      </div>
      <div class="symptom_r fl">
        <p class="clearfix">
          <span  v-for="item in indications">{{item.indicationName}}</span>
          <!--  <span class="active">胸部不适</span><span>呼吸困难</span><span>咳嗽</span><span>胸痛</span>
           <span>四肢无力</span><span class="more fr">更多 <i class="el-icon-arrow-down"></i></span> -->
        </p>
        <p>
          <span class="active">无</span><span>失眠</span><span>咳嗽</span>
        </p>
        <p>
          <span class="active">无</span><span>有病毒感染史</span>
        </p>
        </div>
      </div>
      <div style="background: #fff;margin-top:calc(20/1080*100vh)">
      <div class="may-symptom">
        <p> <label>可能疾病:</label><span>心肌炎</span> <label>诊科室:</label><span>内科 、 心内科</span></p>
        
    </div>
    <div>
          <div class="capacity-title">
            <a style="margin-left:calc(30/1920*100vw)" class='hot-pic' href="#">著名内科医院</a>
          </div>
          <el-row style="padding-left:calc(120/1920*100vw)">
              <el-col :offset="1" :span="8" class='hot-box'><div class="grid-content bg-purple">
                <img  src="../../assets/images/0006.jpeg"/>
                <span>上海市长江医院</span>
                <i>推荐</i>
              </div></el-col>
              <el-col :offset="1" :span="8" class='hot-box'><div class="grid-content bg-purple-light">
                <img  src="../../assets/images/0009.jpeg"/>
                 <span>上海市新华医院（祟明）</span>
              </div></el-col>
              <el-col :offset="1" :span="8" class='hot-box'><div class="grid-content bg-purple">
                <img  src="../../assets/images/0009.jpeg"/>
                 <span>上海市新华医院（祟明）</span>
              </div></el-col>
            </el-row>
        </div>
        
        <div class="card-box">
          <div class="capacity-title">
            <a style="margin-left:calc(30/1920*100vw)" class='hot-pic' href="#">治疗心肌炎常用药</a>
          </div>
          <el-row style="padding-left:calc(120/1920*100vw)">
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
import Footer from "../common//footer";
import Card from "../common/card";
export default {
  components: {
    Header,
    Footer,
    Card
  },
  data() {
    return {
      indications:[],
    };
  },
  methods:{
    getAllIndication(){
      const page = 0;
      this.$axios.get(`http://47.104.99.233:8083/indication/getAll/${page}`).then(res => {
            this.indications = res.data.content;
      })
    }
  },
  mounted(){
    this.getAllIndication();
  }
};
</script>
<style scoped>
.box{
  background-color: #f4f4f4;
}
.capacity-title{
  margin: calc(20/1080*100vh) 0; 
  height: calc(30/1080*100vh) ;
   font-size:  calc(22/1920*100vw);
  line-height:  calc(30/1080*100vh);
  color: #666666;
}
.capacity-title a{
  font-family: 'PingFangSC-Regular';
  font-size: calc(22/1920*100vw);
  color: #666666;
}
.capacity-title .active{
  color: #2873C8;
}
.symptom{
  /* height: 296px; */
  height: calc(296/1080*100vh);
  padding: calc(45/1080*100vh) calc(20/1920*100vw);
  box-sizing: border-box;
}
.symptom_l{
  width: calc(148/1920*100vw);
  height:calc(206/1080*100vh);
  border-right: 2px solid #D8D8D8;
  padding: calc(10/1080*100vh);
  box-sizing: border-box;
}
.symptom_l p{
  margin-bottom: calc(50/1080*100vh);
  font-family: PingFangSC-Regular;
  font-size: calc(22/1920*100vw);
  color: #333333;
}
.symptom_r {
  width: 80%;
  margin-left: calc(53/1920*100vw);
}
.symptom_r p{
  margin-bottom: calc(20/1080*100vh);
}
.symptom_r p span{
  display: inline-block;
  width: calc(150/1920*100vw);
  height: calc(52/1080*100vh);
  color: #666;
  border: 1px solid #666666;
  border-radius: calc(30/1080*100vh);;
  text-align: center;
  line-height: calc(52/1080*100vh);
  margin-right: calc(30/1920*100vw);
  cursor: pointer;
}
.symptom_r p .active{
  color: #2873C8;
  border-color: #2873C8;
}
.symptom_r p .more{
  margin-right: calc(30/1920*100vw);
  color: #2873C8;
  border-color: #2873C8;
}
.may-symptom{
  padding: calc(20/1080*100vh) calc(30/1920*100vw);
  height: calc(30/1080*100vh);
  box-sizing: border-box;
  color: #333;
}
.may-symptom label{
  margin-right: calc(30/1920*100vw);
}
.may-symptom span{
  color: #2873C8;
  margin-right: calc(60/1920*100vw);
}
.capacity-title .hot-pic{
  color: #333;
}
.hot-box{
  width: calc(347/1920*100vw);
  height: calc(349/1080*100vh);
  margin-right: calc(80/1920*100vw);
  text-align: center;
  position: relative;
}
.hot-box div{
  text-align: center;
}
.hot-box img{
 width: calc(347/1920*100vw);
  height: calc(309/1080*100vh);
}
.hot-box span{
  color: #333;
  margin: 0;
}
.card-box{
  margin-top: calc(50/1080*100vh);
}

.hot-box i{
  display: inline-block;
  width: calc(87/1920*100vw);
  height: calc(40/1080*100vh);
  background: #F65353;
  color: #fff;
  position: absolute;
  top: 0;
  right: 0;
  text-align: center;
  line-height: calc(40/1080*100vh);
}
.contanier[data-v-f7fb3e28] {
  margin-top: calc(20/1080*100vh);
}
</style>

