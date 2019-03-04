<template>
  <div class="HButtonTab">
    <ol class="HButtonTab-list">
      <li
        :class="['HButtonTab-list-item',selectIndex===i && 'active']"
        v-for="(item,i) in list"
        :key="i"
        @click="itemClick(i)"
      >{{item.val}}
      </li>
    </ol>
  </div>
</template>
<script>
/*
    *event:on-item-click
    *
    * */
export default {
  model: {
    prop: 'activeIndex',
    event: 'updateActiveIndex'
  },
  props: {
    activeIndex: {
      type: Number
    },
    list: {
      type: Array,
      default () {
        return [];
      }
    }
  },
  data () {
    return {
      selectIndex: this.activeIndex || 0
    };
  },
  methods: {
    itemClick (i) {
      this.selectIndex = i;
      this.$emit('on-item-click', i);
    }
  },
  watch: {
    activeIndex (val) {
      this.selectIndex = val;
    },
    selectIndex (val) {
      this.$emit('updateActiveIndex', val);
    }
  }
};
</script>
<style>

</style>
