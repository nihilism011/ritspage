<template>
  <div class="SignUpBoard">
    <h2>회원가입</h2>
    <label>ID<input v-model="userid" /></label>
    <label>PASSWORD<input v-model="pwd" type="password" /></label>
    <label>NAME<input v-model="username" /></label>
    <button @click="listUp">가입</button>
  </div>
</template>

<script>
import axios from "axios";
export default {
  data() {
    return {
      userid: "",
      pwd: "",
      username: "",
      list: [],
    };
  },

  methods: {
    async listUp() {
      try {
        const response = await axios.post(`http://localhost:3000/insert`, {
          userid: this.userid,
          pwd: this.pwd,
          username: this.username,
        });
        console.log(response.data);
        // 입력 필드 초기화
        this.userid = "";
        this.pwd = "";
        this.username = "";
      } catch (error) {
        console.error("Error during POST request", error);
      }
    },
  },
  mounted() {},
};
</script>

<style scoped lang="scss"></style>
