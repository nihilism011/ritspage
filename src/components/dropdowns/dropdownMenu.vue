<template>
  <div class="dropdown">
    <select name="" id="">
      <option style="display: none">select</option>
      <option>option1</option>
      <option>option2</option>
      <option>option3</option>
    </select>
  </div>
</template>

<script>
export default {};
</script>

<style scoped lang="scss">
/* 전체 드롭다운 스타일 */
.dropdown select {
  appearance: none; /* 기본 브라우저 스타일 제거 */
  -webkit-appearance: none;
  -moz-appearance: none;
  background-color: #ffffff;
  border: 1px solid #ccc;
  border-radius: 4px;
  padding: 10px 38px 10px 16px;
  font-size: 16px;
  cursor: pointer;
  transition: border-color 0.3s, box-shadow 0.3s;
}

/* 드롭다운 아이콘 */
.dropdown {
  position: relative;
  display: inline-block;
}

.dropdown::after {
  content: "\25BC"; /* 화살표 아이콘 */
  position: absolute;
  right: 10px;
  top: 50%;
  transform: translateY(-50%);
  pointer-events: none;
  transition: color 0.3s;
}

/* 호버 효과 */
.dropdown select:hover,
.dropdown select:focus {
  border-color: #888;
  box-shadow: 0 0 5px rgba(0, 0, 0, 0.2);
}

.dropdown select:hover::after,
.dropdown select:focus::after {
  color: #555;
}

/* 드롭다운 옵션 스타일 */
.dropdown select option {
  padding: 10px;
  background-color: #ffffff;
  color: #333;
}
</style>
