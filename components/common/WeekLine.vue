<template>
  <div class="WeekLine">
    <ol class="WeekLine-list">
      <li
        class="WeekLine-list-item"
        v-for="(item,i) in list"
        :key="i"
      >
        <p class="day">{{item.day|convertCnDay}}</p>
        <p :class="['time',item.isMorning && 'active']">{{item.morning}}</p>
        <p :class="['time',item.isAfternoon && 'active']">{{item.afternoon}}</p>
        <span v-if="item.isMorning || item.isAfternoon" class="tipIcon">坐诊</span>
      </li>
    </ol>
    <p v-if="btmTip" class="WeekLine-list-btm-tip">{{btmTip}}</p>
  </div>
</template>
<script>
export default {
  props: {
    list: {
      type: Array,
      default () {
        return [];
      }
    },
    btmTip: {
      type: String
    }
  }
};
</script>
<style>

</style>
