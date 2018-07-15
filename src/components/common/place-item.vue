<template>
  <div class="item-box">
    <img :src='getImgSrc' />
    <div class="right-box">
      <div class="item-title">
        {{datas.name}}
      </div>
      <div class="item-desc">
        <div class="item-place">
          <i class="el-icon-location-outline"></i>
          <span>{{datas.address}}</span>
        </div>
        <div class="item-place">
          <i class="el-icon-phone-outline"></i>
          <span>{{datas.telephone}}</span>
        </div>
        <div class="item-place">
          <i class="el-icon-bell"></i>
          <span>热卖药品：</span> <span v-text='getHotDrug'></span>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  props:{
    datas:{},
    newHotDrugs:''
  },
  methods:{

  }
  ,
  computed:{
    getImgSrc(){
      const datas = this.datas;
      return `http://${datas.fileServerIp}:${datas.fileServerPort}${datas.fileServerPath}${datas.imgUrl}`;
    },
    getHotDrug(){
      const medicines = this.datas.medicines || [];
      let hotDrugs = [];
      medicines.map(item=>{
        if(item.medicineName.genericName)
        hotDrugs.push(item.medicineName.genericName);
      })
     let newHotDrugs = hotDrugs.length>1?hotDrugs.join('|').subString(0,hotDrugs.length-1):hotDrugs.toString();
     return  newHotDrugs;
    }
  }
};
</script>
<style scoped>
.item-box {
  display: flex;
  padding: 20px 0px;
  overflow: hidden;
  border-bottom: 1px solid #e5e5e5;
}
.item-box img {
  width: 311px;
  height: 215px;
  flex: 0 0 311px;
}
.right-box {
  flex: 1;
  position: relative;
  padding: 0 20px;
}
.item-title {
  font-size: 26px;
  color: #333333;
  position: absolute;
  top: 10px;
}
.item-desc {
  position: absolute;
  bottom: 0;
  height: 150px;
  display: flex;
  flex-direction: column;
}
.item-place {
  font-family: PingFangSC-Regular;
  line-height: 50px;
  flex: 1;
}
i {
  color: #2873c8;
}
</style>
