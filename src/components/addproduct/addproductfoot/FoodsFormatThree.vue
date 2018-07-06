<template>
	<div class="bjBox">
		<div class="threeBox">
			<p class="addfor">添加规格</p>
	        <el-form :model="ruleForm" :rules="rules" ref="ruleForm" label-width="100px" class="demo-ruleForm">
	          <el-form-item label="规格" prop="name">
	             <el-input v-model="ruleForm.name"></el-input>
	          </el-form-item>
	        <div class="pack">
			    <p class="bTop">
			      <span class="pack1">包装费</span>
			      <el-input-number v-model="num1" @change="handleChange" :min="0" label="包装费"></el-input-number>
			    </p>
			    <p class="pFoot">
			      <span class="pack2">价格</span>
			      <el-input-number v-model="num2" @change="handleChange" :min="0" label="价格"></el-input-number>
			    </p>
	        </div>
	        <el-form-item class="clearBtn">
	            <el-button type="primary" @click="submitForm('ruleForm'),hideopen()">提交</el-button>
	            <el-button @click="resetForm('ruleForm'),hideopen()">取消</el-button>
	        </el-form-item>
	       </el-form>
	    </div>
	</div>
</template>
<script type="text/ecmascript-6">

	export default{
		 data() {
      return {
      	  num1:0,
          num2:20,
        ruleForm: {
          name: '',
        },
        rules: {
          name: [
            { required: true, message: '请输入规格', trigger: 'blur' },
          ]
        }
      };
    },
    methods: {
    	hideopen(){
    		this.$emit('openhide',false);
    	},
    	handleChange(value) {
            console.log(value);
      },
      submitForm(formName) {
        this.$refs[formName].validate((valid) => {
          if (valid) {
            alert('submit!');
          } else {
            console.log('error submit!!');
            return false;
          }
        });
      },
      resetForm(formName) {
        this.$refs[formName].resetFields();
      }
    }
	}
</script>
<style scoped>
.bjBox{
	width:100%;
	height:100%;
	background: rgba(0,0,0,.4);
	position:fixed;
	left:0;
	top:0;
	z-index:100;
}
.threeBox{
	width:450px;
	height:350px;
	position: absolute;
	left:50%;
	top:50%;
	transform:translate(-50%,-50%);
	background: #fff;
	padding-right:50px;
}
.addfor{
	font-size: 18px;
	font-weight: 600;
	color:#000;
	line-height: 50px;
	padding-left: 20px;
}
.clearBtn{
	clear:both;
}
.pack{
	float:left;
	padding-left:48px;
	font-size: 14px;
    color:#4c576b;
}
.pack1{
	padding-right:8px;
}
.pack2{
	padding-left: 12px;
	padding-right: 10px;
}
.bTop{
	paddint-top:10px;
}
.pFoot{
	padding-top:20px;
    padding-bottom: 20px;
}
	
</style>