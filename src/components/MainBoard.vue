<template>
  <div class="main-board">
    <div>현재 재정비중</div>
    <div>Home탭에 자기소개 등등 추가 예정</div>
    <div>Keyboard 탭 80%완료</div>
    <div>Templates 탭 50%완료 네비게이션 이식 예정</div>
    <div>탭 추가 예정</div>
    <div class="box"></div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      age: 0,
      checkMsg: "",
    };
  },
  methods: {
    check() {
      if (this.age >= 30) {
        this.checkMsg = "이상";
      } else {
        this.checkMsg = "이하";
      }
    },
  },
};
</script>

<style scoped lang="scss">
.main-board {
  display: flex;
  flex-direction: column;
  align-items: center;
  & > div {
    font-size: 40px;
  }
}
@keyframes ani {
  0% {
    transform: rotate(180deg);
  }
  50% {
    transform: rotate(360deg);
  }
  100% {
    transform: rotate(-360deg);
  }
}
.box {
  width: 100px;
  height: 100px;
  border: 1px solid black;
  background: black;
  margin: 40px;
  line-height: 200px;
  animation: ani 3s infinite;
  transition: background-color 2s;
}
</style>
