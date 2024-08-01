<template>
  <div class="BoardBoard">
    <h2>게시판</h2>
    <table>
      <tr>
        <td></td>
      </tr>
    </table>
  </div>
</template>

<script>
import axios from "axios";
export default {
  data() {
    return {
      list: [],
    };
  },

  methods: {
    async listUp() {
      const a = await axios.post(`http://211.244.81.98/aaa/aaa`, {
        id: "mins",
      });
      console.log(a.data);
    },
  },
  mounted() {
    this.listUp();
  },
};
</script>

<style scoped lang="scss"></style>
