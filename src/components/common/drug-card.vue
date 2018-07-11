<template>
  <!-- width:calc(206/1920*100vw);height:calc(200/1080*100vh) -->
  <div :class="{'drug-card-box': true,'drug-card-box-selected':showDesc}">
    <img  :src='getImgSrc' style='width:100%;height:calc(200/1080*100vh)' />
  
    <div class="drug-name">{{drugInfo.medicineName.genericName}}</div>
    <div class="drug-price">¥<span style="font-size: calc(26/1920*100vw);">{{drugInfo.price}}</span>/{{drugInfo.saleUnit}}</div>
    <div class="drug-desc" >
      <div class="desc-title">
        <span>适应症</span>
      </div>
      <div class="desc-content">
        <span>{{drugInfo.indicationDescription}}</span>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  props: {
    showDesc: Boolean,
    drugInfo:{},
    imgSrc:''
  },
  computed:{
    getImgSrc(){
      const drugInfo = this.drugInfo;
      return `http://${drugInfo.fileServerIp}:${drugInfo.fileServerPort}${drugInfo.fileServerPath}${drugInfo.imgUrl}`;
    }
  }
};
</script>
<style scoped>
.drug-card-box {
  width: 100%;
  padding: 40px 30px;
  text-align: center;
  box-sizing: border-box;
  background-color: #fff;
  border-radius: 4px;
  cursor: pointer;
  position: relative;
  border: 1px solid #538fd3;
}
.drug-card-box-selected {
  border: 0;
  border-top: 4px solid #538fd3;
  box-shadow: 0px 1px 20px #ccc;
}
.drug-image {
  height: 280px;
  width: 100%;
}
.drug-name {
  font-size: calc(16/1920*100vw);
  margin-top: calc(28/1080*100vh);
  text-overflow: ellipsis;
  white-space: nowrap;
}
.drug-price {
  color: #f05f5f;
  margin-top: 4px;
}
.drug-desc {
  background-color: #2873c8;
  text-align: left;
  padding: 0 10px;
  padding-bottom: 10px;
  position: absolute;
  bottom: 0;
  left: 0;
  right: 0;
  border-bottom-left-radius: 4px;
  border-bottom-right-radius: 4px;
  /* display: none; */
  opacity: 0;
}
.desc-title {
  color: #fff;
  line-height: 48px;
}
.desc-content {
  color: #fff;
  line-height: 24px;
}
.desc-footer {
  text-align: right;
  padding: 4px 8px;
}
.icon-info {
  display: inline-block;
  text-align: center;
  line-height: 16px;
  width: 20px;
  height: 20px;
  border-radius: 50%;
  border: 2px solid #fff;
  color: #fff;
  vertical-align: middle;
  font-weight: bold;
}
.drug-card-box:hover .drug-desc{
  /* display: inline-block; */
  opacity: .6;
  transition: opacity 1s;
}
</style>

