<template>
  <div>
      <foods-format-three v-show="isOpen" @openhide="hideop"></foods-format-three>
      <p  @click="open3" >
        <el-button type="text" class="addspec">添加规格</el-button>
      </p>
      
      <el-table :data="tableData" style="width: 100%;">
            <el-table-column label="规格" width="180">
      <template slot-scope="scope">
        <span>{{ scope.row.spec }}</span>
      </template>
      </el-table-column>
         <el-table-column  label="包装费"  width="180">
      <template slot-scope="scope">
         <span>{{ scope.row.pack }}</span>
      </template>
      </el-table-column>
     <el-table-column  label="价格"  width="180">
      <template slot-scope="scope">
        <span>{{ scope.row.price }}</span>
      </template>
      </el-table-column>
      <el-table-column label="操作">
        <template slot-scope="scope">
          <el-button
            size="mini"
            type="danger"
            @click="handleDelete(scope.$index, scope.row)">删除</el-button>
        </template>
      </el-table-column>
    </el-table>
    
  </div>
  
</template>

<script type="text/ecmascript-6">
import FoodsFormatThree from "./FoodsFormatThree"
  export default {
    data() {
      return {
        isOpen:false,
        tableData: [{
          spec: '默认',
          pack: '20',
          price: '20'
        }]
      }
    },
    methods: {
      open3(){
        this.isOpen=true;
      },
      hideop(){
        this.isOpen=false;
      },
      handleEdit(index, row) {
        console.log(index, row);
      },
      handleDelete(index, row) {
        console.log(index, row);
      }
    },
    components:{
      FoodsFormatThree
    }
  }
</script>
<style scoped>
.addspec{
  background: #20a1ff;
  color:#fff;
  padding:10px 10px;
  margin-top:30px;
  clear:both;
  float:left;
  margin-left:280px;
}
</style>