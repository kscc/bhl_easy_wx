<template>
  <div class="wrap" >
    <div class="hello display_flex justify-content_flex-center align-items_center"><h2>开发中</h2></div>
    <Footer />
  </div>
</template>

<script>
import Footer from '../components/Footer'
export default {
  name: 'HelloWorld',
  data () {
    return {
      wh: 0
    }
  },
  components: {
      Footer
  },
  created(){
  }

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.hello{text-align:center;height:calc(100% - 3.38rem);}
</style>
