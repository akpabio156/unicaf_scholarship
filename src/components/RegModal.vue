<template>
  <div class="backdrop">
    <div class="box">
      <div class="close">
        <i class="bi bi-check-circle text-success"></i>
      </div>
      <p class="text-center">Registration successfully completed</p>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style scoped>
.backdrop {
  top: 0;
  position: fixed;
  background: rgba(0, 0, 0, 0.5);
  width: 100%;
  height: 100%;
}
.box {
  box-sizing: border-box;
  width: 400px;
  height: 150px;
  margin: auto;
  background: #fff;
  border-radius: 10px;
  padding: 10px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  /* z-index: 1; */
}
@media (min-width: 450px) {
  .box.close {
    margin-bottom: 20px;
  }
}
@media (max-width: 420px) {
  .box {
    box-sizing: border-box;
    width: 300px;
    height: 120px;
    margin: 250px auto;
    background: #fff;
    border-radius: 8px;
    padding: 10px;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    z-index: 3;
  }
}
@media (max-width: 375px) {
  .box {
    box-sizing: border-box;
    width: 300px;
    height: 120px;
    margin: 150px auto;
    background: #fff;
    border-radius: 8px;
    padding: 10px;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    z-index: 3;
  }
}

.box p {
  line-height: 35px;
  font-weight: 400;
  color: var(--blue);
}
.bi-check-circle {
  font-size: 40px;
  font-weight: bold;
}
@media (min-width: 375px) {
}
</style>
