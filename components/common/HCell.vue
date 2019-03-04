<template>
  <div class="HCell">
    <div class="HCell-cnt">
      <slot></slot>
    </div>
    <a
      v-if="hasIcon"
      :href="iconHref">
      <i
        :class="['iconfont',iconClass,'HCell-icon']"
        :style="{color:iconColor}"
      ></i>
    </a>
  </div>
</template>
<script>
export default {
  props: {
    'hasIcon': {
      default: true
    },
    'iconHref': {
      type: String,
      default: 'javascript:;'
    },
    'iconClass': {
      default: 'icon-youjiantou1'
    },
    'iconColor': {
      default: '#707070'
    }
  }
};
</script>
<style>

</style>
