<template>
  <div class="content">
    <div
      class="square"
      ref="square"
      @mouseover="change_color"
      @mouseout="re_color"
    />
    <div class="btn_position">
      <button @click="check_size">Click</button>
    </div>
    <div class="circle" ref="circle" />
    <div class="circle_btn_position_">
      <button @click="change_shape">Change</button>
      <button @click="hide_div">Hide circle</button>
      <button @click="show_div">Show circle</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "praref",
  data() {
    return {
      sq_width: 0,
      sq_height: 0,
      trigger: true,
    };
  },
  methods: {
    check_size() {
      this.$refs.square.clientWidth;
      this.$refs.square.clientHeight;
      alert("Width:" + this.$refs.square.clientWidth);
      alert("Height:" + this.$refs.square.clientHeight);
    },
    change_color() {
      this.$refs.square.style.background = "#E6E6FA";
    },
    re_color() {
      this.$refs.square.style.background = "rgb(72, 70, 145)";
    },
    change_shape() {
      this.$refs.circle.clientHeight = "120px";
      this.$refs.circle.clientWidth = "200px";
    },
    hide_div() {
      this.$refs.circle.style.display = "none";
    },
    show_div() {
      this.$refs.circle.style.display = "block";
    },
  },
  mounted() {
    console.log(this.$refs.square.clientWidth);
    console.log(this.$refs.square.clientHeight);
  },
};
</script>

<style scoped>
.content {
  display: flex;
  flex-wrap: wrap;
}

.square {
  width: 250px;
  height: 250px;
  background-color: rgb(72, 70, 145);
  color: rgb(255, 255, 255);
  text-align: center;
  padding-top: 50%;
}

.circle {
  margin-top: 50px;
  margin-left: 100px;
  width: 600px;
  height: 600px;
  border-radius: 50%;
  background-color: rgb(182, 255, 200);
}
</style>