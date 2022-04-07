<template>
  <div id="app">
 
  

   
      <div v-if="login">
      <v-btn outlined @click="$router.push('/board')">글목록</v-btn>
      <v-btn outlined @click="$router.push(`/user/${user}`)">{{user}}님의 정보</v-btn>
      <v-btn @click="loginOut">로그아웃</v-btn>
      </div>
      <!-- 로그인클릭스 loginView.vue에있는 템플릿나오게하기 -->
      <v-btn v-else @click="$router.push('/login')">로그인</v-btn>
      <!-- <input type="button" value="로그인" v-else @click="$router.push('/login')"> -->
     
    
   

    <v-main>
      <!-- 라우터된 화면이 보이는 공간 -->
        <router-view @login-user="showLogin"/>
    </v-main>
  
  
  </div>
</template>
<script>
export default {
  name :'App',
  data : () =>({
    user :'',
    login : false
  }),
  methods : {
    showLogin : function (user) {
      this.user = user;
      this.login = true;
    },
    loginOut :function () {
      this.user='';
      this.login = false;
      // 첫화면
      this.$router.push('/');
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

nav {
  padding: 30px;
}

nav a {
  font-weight: bold;
  color: #2c3e50;
}

nav a.router-link-exact-active {
  color: #42b983;
}
</style>
