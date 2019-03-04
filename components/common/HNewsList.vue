<template>
  <ol class="HNewsList">
    <li
      class="HNewsList-item"
      v-for="(item , i ) in list"
      :key="i"
      @click="itemClick(item)"
    >
      <div class="HNewsList-item-portrait" v-if="item.imgSrc">
        <img :src="item.imgSrc">
      </div>
      <div class="HNewsList-item-cnt-par">
        <p class="HNewsList-item-cnt-title">{{item.title}}</p>
        <p class="HNewsList-item-cnt">{{item.cnt}}</p>
      </div>
    </li>
  </ol>
</template>
<script>
export default {
  props: {
    list: {
      type: Array
    }
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
