<template>
  <div class="btn-box">
    <button class="R-btn1">Click!</button>
    <button class="R-btn2">Click!</button>
    <button class="R-btn3">Click!</button>
    <button class="R-btn4">Click!</button>
    <button class="R-btn5">Click!</button>
  </div>
</template>

<script>
export default {};
</script>

<style scoped lang="scss">
.R-btn1 {
  margin: 1.5rem;
  color: #6fbfea;
  transition: 0.3s;
  border-radius: 4px;
  border: 1px solid #6fbfea;
  padding: 0.5rem 1rem;
  cursor: pointer;
  background-color: white;
  font-size: 2rem;
  &:hover {
    background-color: #6fbfea;
    color: white;
  }
}
.R-btn2 {
  margin: 1.5rem;
  color: white;
  transition: 0.3s;
  border-radius: 4px;
  border: 1px solid white;
  padding: 0.5rem 1rem;
  cursor: pointer;
  background-color: #6fbfea;
  font-size: 2rem;

  &:hover {
    background-color: white;
    color: #6fbfea;
    border: 1px solid #6fbfea;
  }
}
.R-btn3 {
  margin: 1.5rem;
  color: #fff;
  background-color: #ff4b5c;
  transition: 0.3s;
  border-radius: 4px;
  padding: 0.5rem 1rem;
  cursor: pointer;
  border: none;
  font-size: 2rem;

  &:hover {
    background-color: #ff1c3d;
  }
}

.R-btn4 {
  margin: 1.5rem;
  color: #fff;
  background-color: #6fbfea;
  transition: background-color 0.3s, transform 0.3s;
  border-radius: 4px;
  padding: 0.5rem 1rem;
  cursor: pointer;
  border: none;
  font-size: 2rem;

  &:hover {
    background-color: #5ba6d1;
    transform: scale(1.05);
  }
}

.R-btn5 {
  margin: 1.5rem;
  color: #6fbfea;
  background-color: transparent;
  transition: color 0.3s, background-color 0.3s;
  border-radius: 4px;
  padding: 0.5rem 1rem;
  cursor: pointer;
  border: 1px solid #6fbfea;
  font-size: 2rem;
  &:hover {
    background-color: #6fbfea;
    color: white;
  }
}
</style>
