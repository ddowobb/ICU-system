<template>
  <div class="parent">
    <div class="child">1</div>
    <div class="child">2</div>
    <div class="child">3</div>
    <div class="child">4</div>
    <div class="child">5</div>
    <div class="child">6</div>
  </div>
</template>

<style scoped>
.parent {
  display: flex;
  flex-flow: row;
  flex-wrap: wrap;
  flex-direction: row;
  border: 2px solid blue;
  width: 500px;
  height: 300px;
  justify-content: left;
  /* justify-content >>>  center |  | space-between | space-around | space-evenly*/
  /* align-items: baseline; */
  align-content: stretch;
}

.child {
  width: 100px;
  height: 100px;
  background-color: rgb(184, 80, 80);
}
</style>