<template>
  <div class="main_nav">
    <div class="left_part">
      <div class="logo">ICU作業系統</div>
      <div class="icon" />
      <div class="tail">ICU-2</div>
    </div>
    <div class="right_part">
      <div class="current_time">{{ update_mmdd_time }}</div>
      <div class="time">{{ update_time }}</div>
      <div class="patient">
        <div class="patient_pic" />
        <div class="text">待接病人</div>
      </div>
      <div class="apply">
        <div class="apply_pic" />
        <div class="text">派班申請</div>
      </div>

      <div class="all" @click="open_trigger()">
        <div class="text">全部</div>
        <div class="down_pic" />
        <div class="personal" ref="open_dropdown">
          <div class="personal_text">個人</div>
          <div class="person_pic" />
        </div>
      </div>

      <div class="user">
        <div class="user_pic" />
        <div class="user_text">12345/林美女</div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "mainheader",
  data() {
    return {
      update_time: "",
      update_mmdd_time: "",
    };
  },

  created() {
    setInterval(() => {
      this.get_mmdd_week();
    }, 1000);

    setInterval(() => {
      this.get_hhmm();
    }, 1000);
  },

  methods: {
    get_mmdd_week: function () {
      var today = new Date();
      var mmdd = today.getMonth() + 1 + "月" + today.getDate() + "日";
      var week;
      if (today.getDay() == 0) week = "星期日";
      else if (today.getDay() == 1) week = "星期一";
      else if (today.getDay() == 2) week = "星期二";
      else if (today.getDay() == 3) week = "星期三";
      else if (today.getDay() == 4) week = "星期四";
      else if (today.getDay() == 5) week = "星期五";
      else week = "星期六";
      const result = mmdd + " " + week;
      this.update_mmdd_time = result;
    },

    get_hhmm: function () {
      var today = new Date();
      var hh = today.getHours();
      var mm = today.getMinutes();
      mm = mm > 9 ? mm : "0" + mm;

      if (hh > 12) {
        const afternoon = "下午" + (hh - 12) + ":" + mm;
        this.update_time = afternoon;
      } else {
        const morning = "上午" + hh + ":" + mm;
        this.update_time = morning;
      }
    },

    open_trigger() {
      var dp = this.$refs.open_dropdown;
      if (dp.style.display == "none") {
        dp.style.display = "block";
      } else {
        dp.style.display = "none";
      }
    },
  },

  mounted() {},
};
</script>

<style scoped>
a:link {
  text-decoration: none;
}

a:visited {
  color: white;
  text-decoration: none;
}

.main_nav {
  display: flex;
  flex-flow: row;
  flex-direction: row;
  flex-wrap: nowrap;
  justify-content: space-between;
  align-items: center;
  height: 50px;
  background-color: #4198b9;
  box-shadow: 0px 3px 6px #00000029;
}

.left_part {
  display: flex;
  flex-wrap: nowrap;
  justify-content: center;
  align-items: baseline;
}

.right_part {
  display: flex;
  flex-wrap: nowrap;
  justify-content: center;
  align-items: center;
  background-color: #4198b9;
}

.logo {
  display: flex;
  justify-content: center;
  width: 165px;
  height: 36px;
  font: normal normal bold 25px/36px Arial;
  color: #ffffff;
}

.icon {
  display: flex;
  align-items: baseline;
  /* justify-content: center; 水平 */
  /*align-items: flex-end; 垂直*/
  width: 10px;
  height: 13px;
  background: transparent url("~@/assets/map.png") no-repeat padding-box;
}

.tail {
  display: flex;
  align-items: baseline;
  justify-content: center;
  width: 50px;
  font: normal normal normal 14px/16px Arial;
  letter-spacing: 0.42px;
  color: #c1ebf1;
}

.current_time {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 232px;
  height: 36px;
  font: normal normal normal 25px/29px Arial;
  letter-spacing: 0.75px;
  color: #c1ebf1;
  opacity: 0.8;
}

.time {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 155px;
  height: 36px;
  text-align: left;
  font: normal normal normal 25px/29px Arial;
  letter-spacing: 0.75px;
  color: #ffffff;
}

.patient {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 126px;
  height: 50px;
  background-color: #51bfbd;
}

.patient:hover {
  background-color: #47d1cfed;
}

.patient_pic {
  width: 16px;
  height: 16px;
  background: transparent url("~@/assets/Search.png") no-repeat padding-box;
}

.text {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 80px;
  height: 25px;
  font: normal normal normal 18px/30px Arial;
  letter-spacing: 0.9px;
  color: #ffffff;
}

.apply {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 126px;
  height: 50px;
  background-color: #51bfbd;
}

.apply:hover {
  background-color: #47d1cfed;
}

.apply_pic {
  width: 20px;
  height: 18px;
  background: transparent url("~@/assets/user-profile.png") no-repeat
    padding-box;
}

.all {
  display: flex;
  position: relative;
  justify-content: center;
  align-items: center;
  width: 136px;
  height: 50px;
  background-color: #3d9bb3;
}

.all:hover {
  background-color: #47d1cfed;
}

.down_pic {
  width: 26px;
  height: 26px;
  background: transparent url("~@/assets/Arrow Small Down.png") no-repeat
    padding-box;
}

.personal {
  display: none;
  position: absolute;
  top: 51px;
  width: 136px;
  height: 50px;
  background-color: #246a7c;
  z-index: 1;
}

.personal_text {
  position: absolute;
  top: 11px;
  left: 55px;
  width: 90px;
  height: 25px;
  font: normal normal normal 18px/30px Arial;
  letter-spacing: 0.9px;
  color: #ffffff;
}

.person_pic {
  position: absolute;
  top: 12px;
  left: 25px;
  width: 26px;
  height: 26px;
  background: transparent url("~@/assets/notepad.png") no-repeat padding-box;
}

.personal:hover {
  background-color: #3d9bb3;
}

.user {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 160px;
  height: 50px;
  background-color: #ffffff;
}

.user_pic {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 11px;
  height: 11px;
  background: transparent url("~@/assets/user.png") no-repeat padding-box;
}

.user_text {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 125px;
  height: 25px;
  font: normal normal normal 15px/17px Arial;
  letter-spacing: 0.9px;
  color: #000000;
}
</style>