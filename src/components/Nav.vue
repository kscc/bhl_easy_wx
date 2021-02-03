<template>
  <div class="Nav">
    <ul class="navlist">
      <li :class="$route.meta.sel==0?'cur':''"><a href="javascript:;" @click="goUrl('/',0)">首页</a></li>
      <li :class="$route.meta.sel==1?'cur':''"><a href="javascript:;" @click="goUrl('/jsq',1)">产品计算器</a></li>
      <li :class="$route.meta.sel==2?'cur':''"><a href="javascript:;" @click="goUrl('/newplay',2)">金融产品一览</a></li>
      <li :class="$route.meta.sel==3?'cur':''"><a href="javascript:;" @click="goUrl('/dealer',3)">经销商查询</a></li>
      <li :class="$route.meta.sel==4?'cur':''"><a href="javascript:;" @click="goUrl('/about',4)">关于北现租赁</a></li>
      <li :class="$route.meta.sel==5?'cur':''"><a href="javascript:;" @click="goUrl('/contact',5)">联系我们</a></li>
    </ul>
  </div>
</template>

<script>
export default {
  name:'Nav',
  props:['showNav'],
  data () {
    return {
      showNav1:false,
      sel:0
    }
  },
  created(){
      this.sel = this.$route.meta.sel
  },
  mounted(){
    var _this= this;
    this.$forceUpdate();
    this.sel = this.$route.meta.sel
   
  },
  methods:{
    goUrl:function(path,cur){
      if(cur != this.sel){
        this.$emit('child-event',false)
        this.$router.push({path:path})
        this.sel=cur
      }
    }
  }
}
</script>

<style scoped>
  .Nav{overflow:hidden;padding:0 1rem;margin-left:auto;margin-right:auto;}
  .searchbox{background:url("../assets/search.png") no-repeat left .12rem;background-size:.8rem;margin:1rem 0;display:flex;}
  .searchbox input{flex:1;border:none;background:none;margin:0 .5rem 0 0;border-bottom:1px solid #ccc;font-size:.65rem;padding:0 0 .3rem 1.5rem;}
  .searchbox button{color:#2c73b6;border:.05rem solid #2c73b6;background:none;border-radius:.2rem;padding:.2rem;display:block;width:4rem;height:1.4rem;font-size:.68rem;}
  .navlist{list-style:none;text-align:left;height:calc(100% - 3.8rem);overflow:auto;max-width:1200px;margin:0 auto;}
  .navlist li{border-bottom:1px solid #ececec;}
  .navlist li:last-child{border-bottom:none;}
  .navlist li a{display:block;height:1.8rem;line-height:1.8rem;font-size:.6rem;}
  
</style>
