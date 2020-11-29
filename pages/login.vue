<template>
  <div>
    <el-form :rules="rules">
      <el-form-item class="login-form" props="emil">
        <span><i class="el-icon-mobile" /></span>
        <el-input placeholder="用户名" />
      </el-form-item>
      <el-form-item class="login-form" props="password">
        <span><i class="el-icon-lock" /></span>
        <el-input placeholder="密码" />
      </el-form-item>
      <el-form-item class="login-form" props="code">
        <span><i class="el-icon-lock" /></span>
        <el-input placeholder="验证码" />
        <img :src="captchaImg" @click="handleRefreshCode" />
      </el-form-item>
    </el-form>
  </div>
</template>

<script>
export default {
  layout: 'login',
  data () {
    return {
      rules: {},
      captchaImg: '/api/captcha?t=' + new Date().getTime()
    }
  },
  methods: {
    handleRefreshCode () {
      this.captchaImg = '/api/captcha?t=' + new Date().getTime()
    }
  }
}
</script>

<style lang="less" scoped>
.login-form {
  width: 800px;
  margin: 50px auto;
}
</style>
