<template>
  <div id="app">
    <mainheader />
    <div class="main">
      <content2
        :people="people"
        v-for="(people, index) in people"
        :key="index"
      />
      <!-- <praref /> -->
    </div>
  </div>
</template>

<script>
import content2 from "./components/content_2.vue";
import mainheader from "./components/header.vue";
import praref from "./components/praref.vue";

export default {
  name: "App",
  components: {
    content2,
    mainheader,
    praref,
  },
  data() {
    return {
      people: [
        {
          id: 1,
          name: "王O明",
          number: 1234567890,
          tag_num: "A",
          rating: 14,
          room_num: "9I2-01",
          doctor: "劉忠政",
          department: "腸胃科",
          nurse: "林美女",
          sex: "male",
        },
        {
          id: 2,
          name: "蔡O美",
          number: 1234567890,
          tag_num: "B",
          rating: 14,
          room_num: "9I2-02",
          doctor: "張建榮",
          department: "心內科",
          nurse: "林美女",
          sex: "female",
        },
        {
          id: 3,
          name: "John William Waterhouse",
          number: 1234567890,
          tag_num: "A",
          rating: 16,
          room_num: "9I2-03",
          doctor: "蔡慶宏",
          department: "胸內科",
          nurse: "林美女",
          sex: "male",
        },
        {
          id: 4,
          name: "陳O賢",
          number: 1234567890,
          tag_num: "C",
          rating: 14,
          room_num: "9I2-05",
          doctor: "陳昶旭",
          department: "腎臟科",
          nurse: "陳佳怡",
          sex: "male",
        },
        {
          id: 5,
          name: "",
          number: "",
          tag_num: "",
          rating: "",
          room_num: "9I2-06",
          doctor: "",
          department: "",
          nurse: "",
          sex: "",
        },
        {
          id: 6,
          name: "林O宏",
          number: 1234567890,
          tag_num: "A",
          rating: 16,
          room_num: "9I2-07",
          doctor: "鄒順生",
          department: "一外科",
          nurse: "楊詩涵",
          sex: "male",
        },
        {
          id: 7,
          name: "劉O傑",
          number: 1234567890,
          tag_num: "A",
          rating: 14,
          room_num: "9I2-08",
          doctor: "陳昶旭",
          department: "腎臟科",
          nurse: "楊詩涵",
          sex: "male",
        },
        {
          id: 8,
          name: "李O蘭",
          number: 1234567890,
          tag_num: "B",
          rating: 14,
          room_num: "9I2-09",
          doctor: "張建榮",
          department: "心內科",
          nurse: "林美女",
          sex: "female",
        },
        {
          id: 9,
          name: "楊O婷",
          number: 1234567890,
          tag_num: "B",
          rating: 14,
          room_num: "9I2-10",
          doctor: "蔡慶宏",
          department: "胸內科",
          nurse: "陳佳怡",
          sex: "female",
        },
        {
          id: 10,
          name: "梁O明",
          number: 1234567890,
          tag_num: "A",
          rating: 14,
          room_num: "9I2-11",
          doctor: "劉忠政",
          department: "腸胃科",
          nurse: "陳佳怡",
          sex: "male",
        },
        {
          id: 11,
          name: "陳O美",
          number: 1234567890,
          tag_num: "B",
          rating: 14,
          room_num: "9I2-12",
          doctor: "劉忠政",
          department: "腸胃科",
          nurse: "楊詩涵",
          sex: "female",
        },
        {
          id: 12,
          name: "石O維",
          number: 1234567890,
          tag_num: "A",
          rating: 14,
          room_num: "9I2-13",
          doctor: "劉忠政",
          department: "腸胃科",
          nurse: "林詩涵",
          sex: "male",
        },
        {
          id: 13,
          name: "王O明",
          number: 1234567890,
          tag_num: "A",
          rating: 14,
          room_num: "9I2-15",
          doctor: "劉忠政",
          department: "腸胃科",
          nurse: "林美女",
          sex: "male",
        },
        {
          id: 14,
          name: "王O明",
          number: 1234567890,
          tag_num: "A",
          rating: 14,
          room_num: "9I2-16",
          doctor: "劉忠政",
          department: "腸胃科",
          nurse: "林美女",
          sex: "male",
        },
        {
          id: 15,
          name: "王O明",
          number: 1234567890,
          tag_num: "A",
          rating: 14,
          room_num: "9I2-17",
          doctor: "劉忠政",
          department: "腸胃科",
          nurse: "林美女",
          sex: "male",
        },
        {
          id: 16,
          name: "蔡O美",
          number: 1234567890,
          tag_num: "B",
          rating: 14,
          room_num: "9I2-18",
          doctor: "劉忠政",
          department: "腸胃科",
          nurse: "林美女",
          sex: "female",
        },
        {
          id: 17,
          name: "蔡O美",
          number: 1234567890,
          tag_num: "B",
          rating: 14,
          room_num: "9I2-19",
          doctor: "劉忠政",
          department: "腸胃科",
          nurse: "林美女",
          sex: "female",
        },
        {
          id: 18,
          name: "王O明",
          number: 1234567890,
          tag_num: "A",
          rating: 14,
          room_num: "9I2-20",
          doctor: "劉忠政",
          department: "腸胃科",
          nurse: "林美女",
          sex: "male",
        },
        {
          id: 19,
          name: "蔡O美",
          number: 1234567890,
          tag_num: "B",
          rating: 14,
          room_num: "9I2-21",
          doctor: "劉忠政",
          department: "腸胃科",
          nurse: "林美女",
          sex: "female",
        },
        {
          id: 20,
          name: "王O明",
          number: 1234567890,
          tag_num: "A",
          rating: 14,
          room_num: "9I2-22",
          doctor: "劉忠政",
          department: "腸胃科",
          nurse: "林美女",
          sex: "male",
        },
      ],
    };
  },
};
</script>

<style>
.main {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  padding-top: 40px;
  padding-left: 45px;
  padding-right: 45px;
  padding-bottom: 300px;
}

.main::after {
  content: "";
  margin-left: 30px;
  margin-right: 1170px;
  /* flex: 5; */
}
</style>
