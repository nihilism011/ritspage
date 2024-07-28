<template>
  <div class="keyboard-board">
    <div v-for="item in items" :key="item.name" class="keyboard">
      <div class="keybodardImg">
        <img :src="require(`../assets/${item.imgs}`)" />
        <div class="img-click" @click="$emit('name-click', item)">상세보기</div>
      </div>
      <h3 @click="$emit('name-click', item)">{{ item.name }}</h3>
      <p>{{ item.chuk }}</p>
      <div>
        <button @click="item.cnt++">Click!</button>
        <span>추천수 : {{ item.cnt }}</span>
      </div>
    </div>
  </div>
</template>

<script>
import keyboards from "../data/keyboards.json";
export default {
  data() {
    return {
      items: keyboards,
    };
  },
  methods: {},
};
</script>

<style scoped>
.keybodardImg {
  position: relative;
  width: 100%;
  height: auto;
  margin-top: 40px;
}
.keybodardImg img {
  width: 100%;
  height: 375px;
  display: block;
}
.keyboard-board {
  display: flex;
  flex-flow: row wrap;
}
.keyboard {
  display: flex;
  flex-direction: column;
  width: 300px;
  text-align: center;
  align-items: center;
  margin: 20px;
}
.img-click {
  background: rgba(0, 0, 0, 0.5);
  color: white;
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  opacity: 0;
  transition: opacity 0.3s ease;
  cursor: pointer;
}
.keybodardImg:hover .img-click {
  opacity: 1;
}
.keyboard button {
  margin: 1rem;
  color: #6fbfea;
  transition: 0.3s;
  border-radius: 4px;
  border: 1px solid #6fbfea;
  padding: 0.5rem 1rem;
  cursor: pointer;
  background-color: transparent;
  font-size: 15px;
}
.keyboard button:hover {
  background-color: #6fbfea;
  color: white;
}
</style>
