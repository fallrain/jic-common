<template>
<div class="HTextarea">
  <textarea
    class="HTextarea-ta"
    :placeholder="placeHolder"
    :maxlength="maxNumber"
    v-model="taValue"
  ></textarea>
  <p class="HTextarea-fontNumber">{{taValueLength}}/{{maxNumber}}</p>
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
    }
  },
  data () {
    return {
      taValue: this.value
    };
  },
  watch: {
    taValue (newV, oldV) {
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
