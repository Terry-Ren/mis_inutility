<template>
  <div class=container>
    <div class="title">
      <h1>吾爱吾理</h1>
      <h2>交互式校园全景地图</h2>
    </div>
    <pano :class="{'hidden':first}" width="1000" height="560" debug bundle="static/1/" format="jpg"></pano>
    <pano :class="{'hidden':second}"  title="" width="1000" height="560" debug bundle="static/2/" format="jpg"></pano>
    <pano :class="{'hidden':third}" title="" width="1000" height="560" debug bundle="static/3/" format="jpg"></pano>
    <div id="fontdiv" class="fontdiv"></div>
    <div class="pushtext">
      <textarea id="message" maxlength="15"></textarea>
      <div onclick="pushtext()" class="pushbtn">发送</div>
    </div>
    <div class="lunbo">
          <VaCarousel :items="items" height="140px" width="100%" total="2" @selectedItem="selectItem"/>
    </div>
  </div>
</template>
<script type="text/ecmascript-6">
import Pano from "vue-pano";
import VaCarousel from "va-carousel/src/components/VaCarousel";
export default {
  data() {
    return {
      bundle: "static/1/",
      first:false,
      second:true,
      third:true,
      items: [
        {
          id: 1,
          src: "../../static/all/1.jpg"
        },
        {
          id: 2,
          src: "../../static/all/2.jpg"
        },
        {
          id: 3,
          src: "../../static/all/3.jpg"
        }
      ]
    };
  },
  components: {
    Pano,
    VaCarousel
  },
  methods: {
    selectItem(obj, item) {
      console.log(obj.id)
      if (obj.id == 1) {
        this.first=false
        this.second=true
        this.third=true
      } else if (obj.id == 2) {
        this.first=true
        this.second=false
        this.third=true

      }else{
        this.first=true
        this.second=true
        this.third=false
      }
    }
  }
};
</script>
<style scoped lang="scss">
.container {
  padding: 0 300px;
  position: relative;
  .title {
    position: absolute;
    left: 2vw;
  }
  .lunbo {
    position: absolute;
    bottom: 8vh;
    left: 23vw;
    width: 900px;
  }
}
.hidden{
  display: none;
}
</style>
