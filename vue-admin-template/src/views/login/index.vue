<template>
  <div id="app">
    <div class="middles">
      <div class="middle">
        <img class="img" src="../../assets/图片.png" />
<div style="margin: 20px;"></div>
<el-form :label-position="labelPosition"  :model="formLabelAlign">
  <el-form-item :rules="[ { required: true, message: '请输入用户名', trigger: 'blur' },]">
    <el-input v-model="formLabelAlign.name" placeholder="请输入账号" >
    <i slot="prefix" class="el-icon-mobile"></i>
    </el-input>
  </el-form-item>
  <el-form-item>
    <el-input  v-model="formLabelAlign.region" :type="this.change===true? 'password' : 'text'" placeholder="请输入密码" >
    <i slot="prefix" class="el-icon-lock"></i>
    <i @click="btnChange" slot="suffix" v-if="change" class="el-icon-user-solid"></i>
    <i @click="btnChange" slot="suffix" v-else class="el-icon-user"></i>
    </el-input>
  </el-form-item>
  <el-form-item>
    <el-input v-model="formLabelAlign.type" class="inputEnd" placeholder="请输入验证码">
    <i slot="prefix" class="el-icon-folder-checked"></i>
    <!-- <i slot="append">123</i> -->
    </el-input>
    <el-input v-model="formLabelAlign.type" class="inputs" placeholder="验证码区域"></el-input>
  </el-form-item>
  <div class="logins">
    <el-form-item>
    <el-button type="primary" class="login">提交</el-button>
  </el-form-item>
  </div>
</el-form>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
        labelPosition: 'right',
        formLabelAlign: {
          name: 'admin',
          region: '123456',
          type: ''
        },
        change: true
    }
  },

  created () {

  },

  methods: {
    btnChange(){
      this.change = !this.change
      console.log(111)
  }
  }
}
</script>

<style scoped lang="scss">
.middles{
    position: relative;
    height: 100%;
    width: 100%;
    overflow: hidden;
    background-image: url(../../assets/背景图.png);
    background-repeat: no-repeat;
    background-size: cover;
}
.middle{
    position: absolute;
    width: 518px;
    height: 388px;
    top: 50%;
    left: 50%;
      transform: translate(-50%, -50%);
    background: #fff;
    padding: 76px 35px 0;
    border-radius: 10px;
}
.img{
  position: absolute;
    width: 96px;
    height: 96px;
    top: -46px;
    left: 50%;
    margin-left: -48px;
}
.el-icon-mobile{
  font-size:19px;
}
.el-icon-lock{
  font-size:19px;
}
.el-icon-folder-checked{
   font-size:19px;
}
.inputEnd{
  width: 60%;
}
.inputs{
  width:40%;
}
.el-input__inner{
  height: 39px;
}
// /deep/.el-form-item .is-required{
//   // height:52px;
// }
.logins{
  display:flex;
  justify-content:center;
  width: 450px;
  height: 50px;
}
.login{
  // margin-left: 100px;
     width: 450px;
    height: 50px;
      background: linear-gradient(262deg,#2e50e1,#6878f0);
}
</style>
