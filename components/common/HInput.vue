<template>
<div class="HInput">
  <input
    :type="type"
    class="HInput-ipt"
    :placeholder="placeHolder"
    :maxlength="maxNumber"
    v-model="iptValue"
  >
</div>
</template>
<script>
export default {
  props: {
    type: {
      type: String,
      default: 'text'
    },
    value: {
      type: String
    },
    maxNumber: {
      type: Number,
      default: 100
    },
    placeHolder: {
      type: String,
      default: '请输入'
    }
  },
  data () {
    return {
      iptValue: this.value
    };
  },
  watch: {
    iptValue (newV, oldV) {
      if (oldV !== newV) {
        this.$emit('input', newV);
        this.$emit('change', newV);
      }
    }
  },
  computed: {
    taValueLength () {
      return this.taValue.length;
    }
  }
};
</script>
<style>

</style>
