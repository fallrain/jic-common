<template>
  <ul class="SimpleList">
    <li
      class="SimpleList-item"
      v-for="(item,key) in data"
      :key="key"
      @click="itemClick(item)"
    >
      <img
        class="SimpleList-item-img"
        :src="item.imgSrc || imgSrc"
      >
      <div class="SimpleList-item-cnt">
        <title class="SimpleList-item-cnt-title">{{item.title}}</title>
        <p class="SimpleList-item-detail">{{item.detail}}</p>
      </div>
      <div class="SimpleList-item-arrow">
        <i class="iconfont icon-youjiantou"></i>
      </div>
    </li>
  </ul>
</template>
<script>
import defaultImg from '@/assets/img/defaultDepPortrait.png';

export default {
  props: ['data'],
  data () {
    return {
      imgSrc: defaultImg
    };
  },
  methods: {
    itemClick (item) {
      this.$emit('item-click', item);
    }
  }
};
</script>
<style>
</style>
