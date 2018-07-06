<template>
  <div class="formatone">
    <p>
      <span class="spec">包装费</span>
      <el-input-number v-model="num1" @change="handleChange" :min="0" label="包装费"></el-input-number>
    </p>
    <p class="price">
      <span  class="spec specprice">价格</span>
      <el-input-number v-model="num2" @change="handleChange" :min="0" label="价格"></el-input-number>
    </p>
      
  </div>
  
</template>
<script>
  export default {
    data() {
      return {
        num1: 0,
        num2:0
      };
    },
    methods: {
      handleChange(value) {
        console.log(value);
      }
    }
  };
</script>
<style scoped>
.formatone{
  clear:both;
  float:left;
  padding-left:45px;
  padding-top: 20px;
}
.spec{
  font-size: 14px;
  color:#4c576b;
  padding-right:10px;
}
.specprice{
  padding-left:10px;
}
.price{
  padding-top: 20px;
  padding-left:5px;
  padding-bottom: 10px;
}
</style>