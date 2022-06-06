<template>
  <div class="board" v-if="people.name.length > 0">
    <div class="sidebar" :class="people.sex == 'female' ? 'pink' : 'blue'">
      <div class="pic" :class="people.sex == 'female' ? 'female' : 'male'" />
      <div>
        <div class="num">{{ people.number }}</div>
        <div class="name">
          {{ people.name }}
          <div class="tooltiptext">{{ people.name }}</div>
        </div>
      </div>
      <div>
        <div class="sidebar_tag" :style="tagStyle(people.tag_num)">
          <div class="tag_text">{{ people.tag_num }}</div>
        </div>

        <div class="rating" :style="ratingStyle(people.rating)">
          <div class="rating_text">{{ people.rating }}</div>
        </div>
      </div>
    </div>
    <div class="boardbed_white">
      <div class="bed_num">{{ people.room_num }}</div>
      <div class="line" />
      <div>
        <div class="doctor">主治醫生:{{ people.doctor }}</div>
        <div class="department">主治科別:{{ people.department }}</div>
      </div>
    </div>
    <div class="bottom">護理人員:{{ people.nurse }}</div>
  </div>
  <div v-else class="board">
    <div class="no_text">{{ people.room_num }}</div>
  </div>
</template>

<script>
export default {
  name: "content",
  props: {
    people: Object,
  },
  data() {
    return {};
  },
  methods: {
    tagStyle(tag) {
      if (tag == "A") {
        return { "background-color": "#e66c6c" };
      }
      if (tag == "B") {
        return { "background-color": "#f89b05" };
      }
      return { "background-color": "#47b281" };
    },
    ratingStyle(rating) {
      if (rating == "14") {
        return { "background-color": "#127D46" };
      }
      return { "background-color": "#CC4962" };
    },
  },
  mounted() {},
};
</script>

<style scoped>
.board {
  position: relative;
  width: 280px;
  height: 200px;
  background-color: #f7f7f7;
  box-shadow: 0px 0px 10px #00000029;
  border-radius: 8px;
  margin-bottom: 30px;
}

.sidebar {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 280px;
  height: 85px;
  border-radius: 8px 8px 0px 0px;
}

.blue {
  background-color: #d0f0f4;
}

.pink {
  background-color: #f4dfe7;
}

.pic {
  width: 45px;
  height: 45px;
}

.male {
  background: transparent url(~@/assets/boy.png);
}

.female {
  background: transparent url(~@/assets/girl.png);
}

.num {
  margin-top: 5px;
  margin-left: 10px;
  font: normal normal normal 16px/21px Arial;
  color: #233044;
}

.name {
  margin-top: 5px;
  margin-left: 10px;
  display: inline-block;
  width: 120px;
  font: normal normal normal 26px/28px Arial;
  color: #101b31;
  overflow: hidden;
  text-overflow: ellipsis;
  white-space: nowrap;
}

.sidebar_tag {
  margin-top: -25px;
  margin-left: 30px;
  width: 25px;
  height: 25px;
  border-radius: 999px;
}

.tag_text {
  width: 12px;
  height: 22px;
  text-align: center;
  font: normal normal bold 16px/22px Arial;
  letter-spacing: 3.2px;
  color: #ffffff;
  padding-top: 2px;
  margin-left: 7px;
  margin-right: 6px;
}

.rating {
  margin-top: -25px;
  margin-left: 60px;
  width: 25px;
  height: 25px;
  border-radius: 999px;
  text-align: center;
}

.rating_text {
  width: 12px;
  height: 22px;
  text-align: center;
  font: normal normal bold 16px/20px Arial;
  color: #ffffff;
  padding-top: 3px;
  padding-left: 3px;
}

.sidebar_null {
  width: 280px;
  height: 200px;
  background-color: #f7f7f7;
  box-shadow: 0px 0px 10px #00000029;
  border-radius: 8px;
}

.boardbed_white {
  position: relative;
  width: 280px;
  height: 73px;
  background-color: #ffffff;
  display: flex;
  justify-content: center;
  align-items: center;
}

.bed_num {
  width: 90px;
  height: 33px;
  font: normal normal normal 30px/30px Arial;
  color: #064846;
}

.line {
  margin-left: 10px;
  width: 4px;
  height: 50px;
  background-color: #489795;
  border-radius: 5px;
}

.doctor {
  margin-left: 10px;
  width: 125px;
  height: 22px;
  font: normal normal normal 16px/22px Arial;
  color: #064846;
}

.department {
  margin-top: 5px;
  margin-left: 10px;
  width: 125px;
  height: 22px;
  text-align: left;
  font: normal normal normal 16px/22px Arial;
  color: #064846;
}

.bottom {
  width: 280px;
  height: 42px;
  font: normal normal normal 18px/22px Arial;
  color: #08092d;
  display: flex;
  justify-content: center;
  align-items: center;
}

.tooltiptext {
  visibility: hidden;
  width: 180px;
  font-size: 15px;
  background-color: black;
  color: #fff;
  text-align: center;
  border-radius: 6px;
  padding: 5px 0;
  position: absolute;
  top: 35%;
  left: 25%;
  margin-left: -60px;
  z-index: 1;
}

.tooltiptext::after {
  content: "";
  position: absolute;
  bottom: 100%;
  left: 50%;
  margin-left: -5px;
  border-width: 5px;
  border-style: solid;
  border-color: transparent transparent black transparent;
}

.name:hover .tooltiptext {
  visibility: visible;
}

.no_text {
  margin-top: 90px;
  margin-left: 95px;
  width: 86px;
  height: 33px;
  font: normal normal normal 30px/30px Arial;
  color: #c3c4c9;
}
</style>