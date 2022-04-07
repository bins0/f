<template>

 
  <v-container>
      <v-card>
          <v-text-field label="아이디" v-model="user"></v-text-field>
          <v-text-field label="패스워드"></v-text-field>
          <v-card-actions>
          <v-btn @click="loginUser">로그인</v-btn>
          <v-btn @click="$router.push('/')">취소</v-btn>
          </v-card-actions>
      </v-card>
  </v-container> 
</template>

<script>

export default {
  name: 'LoginView',
  data : () => ({
      user : ''
  }),
  methods : {
    //   login-user 이벤트를 보내고,this.user값을 전달
      loginUser : function () {
          this.$emit('login-user',this.user)
        //   컴포넌트를  '/'로바꿈 push사용
         this.$router.push('/');
      }
  }
}
</script>