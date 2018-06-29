<template>
<div class=container>
    <div class="title">
        <h1>吾爱吾理</h1>
        <h2>交互式校园全景地图</h2>
    </div>
<pano title="" width="800" height="580" debug bundle="static/pantry/" format="jpg"></pano>
<div id="fontdiv" class="fontdiv"></div>
    <div class="pushtext">  
        <textarea id="message" maxlength="15" ></textarea>  
        <div onclick="pushtext()" class="pushbtn">发送</div>  
    </div>  
</div>
    <!-- built files will be auto injected -->
    
</template>
<script type="text/ecmascript-6">
import Pano from "vue-pano";
export default {
  components: { Pano }
};
</script>
<style scoped lang="scss">
.container{
    padding: 0 300px;
    position: relative;
    .title{
        position: absolute;
        left: 2vw;

    }
}
</style>


