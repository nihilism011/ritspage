<template>
  <div class="templates-board">
    <div id="contents">
      <div v-for="item in templates" :key="item.id" :id="item.id">
        <h2>{{ item.title }}</h2>
        <div class="display">
          <div class="show-box">
            <component :is="item.component" />
          </div>
        </div>
      </div>
    </div>
    <div id="templatesNavi">
      <h3>Menu</h3>
      <div
        v-for="item in templates"
        :key="item.id"
        @click="scrollShowBox(item.id)"
      >
        {{ item.title }}
      </div>
    </div>
  </div>
</template>

<script>
import templates from "../data/templates.json";
import btn1 from "./buttons/radiusBtn.vue";
import drop1 from "./dropdowns/dropdownMenu.vue";
import rDrop from "./dropdowns/rightDropdownMenu.vue";
import lDrop from "./dropdowns/leftDropdownMenu.vue";

export default {
  components: {
    btn1,
    drop1,
    rDrop,
    lDrop,
  },
  data() {
    return {
      templates,
    };
  },
  methods: {
    scrollShowBox(boxid) {
      const element = document.getElementById(boxid);
      if (element) {
        element.scrollIntoView({ behavior: "smooth" });
      }
    },
  },
};
</script>

<style scoped lang="scss">
.templates-board {
  display: grid;
  grid-template-columns: auto 200px;
}
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
  width: 100%;
  margin: 10px;
  box-shadow: 2px 2px 6px;
  transition: background-color 0.5s;
}
#templatesNavi {
  background: darkslateblue;
  color: white;
  width: 200px;
  padding: 15px;
  border-radius: 5px;
  position: fixed;
  right: 0;
  top: 100px;

  & h3 {
    background: white;
    color: darkslateblue;
    padding: 10px;
    border-radius: 5px;
    margin-bottom: 15px;
  }
}
</style>
