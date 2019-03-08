<template>
    <div>
      <form v-if="isLogin">
        用户名
        <input type="text" v-model="name">
        <br>
        密码
        <input type="password" v-model="password">
        <button type="button" @click="login">登陆</button>
        <button type="button" @click="isLogin=false">注册</button>
      </form>
      <form  v-else>
        用户名
        <input type="text" v-model="name">
        <br>
        密码
        <input type="password" v-model="password">
        <br>
        再次确认密码
        <input type="text">
        <br>
        <button type="button" @click="addUser">確認</button>
        <button type="button" @click="isLogin=true">キャンセル</button>
      </form>
    </div>
</template>

<script>
export default {
  name: 'Login',
  data () {
    return {
      isLogin: true,
      name: '',
      password: ''
    }
  },
  methods: {
    login () {
      this.$router.push('/home/list')
    },
    addUser () {
      localStorage.setItem('name', this.name)
      localStorage.setItem('password', this.password)
    }
  }
}
</script>

<style scoped>

</style>
