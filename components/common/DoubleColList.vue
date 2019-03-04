<template>
  <div
    class="DoubleColList"
  >
    <ol class="DoubleColList-right">
      <li
        class="DoubleColList-right-item"
        v-for="(rItem,rIndex) in rightList"
        :key="rIndex"
        @click="rightItemClick(rIndex,rItem)"
      >
        <div
          v-if="rItem.name"
          class="DoubleColList-right-title"
        >
          <span class="name">{{rItem.name}}</span>
          <span class="type" v-if="rItem.type">{{rItem.type}}</span>
        </div>
        <p
          class="DoubleColList-right-cnt"
        >{{rItem.inf}}</p>
      </li>
    </ol>
    <ol
      :style="{width:leftWidth+'px'}"
      class="DoubleColList-left"
    >
      <li
        :class="['DoubleColList-left-item',itemKey===choosedIndex && 'active']"
        v-for="(item,itemKey) in list"
        :key="itemKey"
        @click="leftItemClick(itemKey,item)"
        :ref="'DoubleColListLeftItem' + itemKey"
      >
        <div class="DoubleColList-left-item-cnt">
          <i
            v-if="item.icon"
            :class="['iconfont',item.icon]"
          ></i>
          {{item.name}}
        </div>
      </li>
    </ol>
  </div>
</template>
<script>
export default {
  props: {
    list: {
      default: []
    },
    choosedIndex: {
      default: 0
    },
    leftWidth: {
      default: 138
    }
  },
  data () {
    return {
    };
  },
  computed: {
    rightList () {
      if (typeof this.choosedIndex !== 'number') {
        return [];
      }
      return (this.list && this.list.length) ? this.list[this.choosedIndex].childList : [];
    }
  },
  methods: {
    leftItemClick (index, item) {
      this.$emit('left-item-click', index, item);
    },
    rightItemClick (index, item) {
      this.$emit('right-item-click', index, item);
    }
  }
};

</script>
<style>

</style>
