<template>
<div class="HSelect">
  <select
    class="HSelect-slt"
    :placeholder="placeHolder"
    v-model="sltValue"
  >
    <option value="">请选择</option>
    <option
      v-for="(item) in data"
      :key="item.key"
      :value="item.key"
    >{{item.val}}</option>
  </select>
</div>
</template>
<script>
export default {
  props: {
    value: {
      type: String
    },
    maxNumber: {
      type: Number,
      default: 200
    },
    placeHolder: {
      type: String,
      default: '请输入'
    },
    data: {
      type: Array
    }
  },
  data () {
    return {
      sltValue: this.value
    };
  },
  watch: {
    sltValue (newV, oldV) {
      if (oldV !== newV) {
        this.$emit('change', newV);
        this.$emit('input', newV);
      }
    }
  },
  computed: {
  }
};
</script>
<style>

</style>
