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

    <div class="symptom clearfix" style="background: #fff;margin-top:10px">
      <div class="symptom_l fl">
        <p>主要症状</p>
        <p>伴随症状</p>
        <p>相关信息</p>
      </div>
      <div class="symptom_r fl">
        <p class="clearfix">
           <span class="active">胸部不适</span><span>呼吸困难</span><span>咳嗽</span><span>胸痛</span>
           <span>四肢无力</span><span class="more fr">更多 <i class="el-icon-arrow-down"></i></span>
        </p>
        <p>
          <span class="active">无</span><span>失眠</span><span>咳嗽</span>
        </p>
        <p>
          <span class="active">无</span><span>有病毒感染史</span>
        </p>
        </div>
      </div>
      <div style="background: #fff;margin-top:20px">
      <div class="may-symptom">
        <p> <label>可能疾病:</label><span>心肌炎</span> <label>诊科室:</label><span>内科 、 心内科</span></p>
        
    </div>
    <div>
          <div class="capacity-title">
            <a style="margin-left:30px" class='hot-pic' href="#">著名内科医院</a>
          </div>
          <el-row style="padding-left:120px">
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
            <a style="margin-left:30px" class='hot-pic' href="#">治疗心肌炎常用药</a>
          </div>
          <el-row style="padding-left:120px">
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
    
    };
  }
};
</script>
<style>
.box{
  background-color: #f4f4f4;
}
.capacity-title{
  margin: 20px 0;
  height: 30px;
   font-size: 22px;
  line-height: 30px;
  color: #666666;
}
.capacity-title a{
  font-family: 'PingFangSC-Regular';
  font-size: 22px;
  color: #666666;
}
.capacity-title .active{
  color: #2873C8;
}
.symptom{
  height: 296px;
  padding: 45px 20px;
  box-sizing: border-box;
}
.symptom_l{
  width: 148px;
  height: 206px;
  border-right: 2px solid #D8D8D8;
  padding: 10px;
  box-sizing: border-box;
}
.symptom_l p{
  margin-bottom: 50px;
  font-family: PingFangSC-Regular;
  font-size: 22px;
  color: #333333;
}
.symptom_r {
  width: 80%;
  margin-left: 53px;
}
.symptom_r p{
  margin-bottom: 20px;
}
.symptom_r p span{
  display: inline-block;
  width: 150px;
  height: 52px;
  color: #666;
  border: 1px solid #666666;
  border-radius: 30px;
  text-align: center;
  line-height: 52px;
  margin-right: 30px;
  cursor: pointer;
}
.symptom_r p .active{
  color: #2873C8;
  border-color: #2873C8;
}
.symptom_r p .more{
  margin-right: 30px;
  color: #2873C8;
  border-color: #2873C8;
}
.may-symptom{
  padding: 20px 30px;
  height: 30px;
  box-sizing: border-box;
  color: #333;
}
.may-symptom label{
  margin-right: 30px;
}
.may-symptom span{
  color: #2873C8;
  margin-right: 60px;
}
.capacity-title .hot-pic{
  color: #333;
}
.hot-box{
  width: 347px;
  height: 349px;
  margin-right: 80px;
  text-align: center;
  position: relative;
}
.hot-box div{
  text-align: center;
}
.hot-box img{
  width: 347px;
  height: 309px;
}
.hot-box span{
  color: #333;
  margin: 0;
}
.card-box{
  margin-top: 50px;
}

.hot-box i{
  display: inline-block;
  width: 87px;
  height: 40px;
  background: #F65353;
  color: #fff;
  position: absolute;
  top: 0;
  right: 0;
  text-align: center;
  line-height: 40px;
}
.contanier[data-v-f7fb3e28] {
  margin-top: 20px;
}
</style>

