<template>
  <div class="templates-board">
    <div id="contents">
      <div id="Dropdown">
        <h2>Button</h2>
        <div class="display">
          <div class="show-box">
            <btn1 />
          </div>
        </div>
      </div>
      <div id="Animation">
        <h2>Animation</h2>
        <div class="display"><div class="show-box"></div></div>
      </div>
      <div id="code">
        <h2>code</h2>
        <div class="display"><div class="show-box"></div></div>
      </div>
    </div>
  </div>
</template>

<script>
import btn1 from "./buttons/radiusBtn.vue";

export default {
  components: {
    btn1,
  },
};
</script>

<style scoped>
#contents > div {
  margin-top: 100px;
}
.display {
  display: flex;
  margin: 20px;
}
.show-box {
  display: flex;
  flex-direction: column;
  background-color: #1e1e1e;
  border-radius: 10px;
  height: 400px;
  width: 60%;
  margin: 10px;
  box-shadow: 2px 2px 6px;
  transition: background-color 0.5s;
}
</style>
