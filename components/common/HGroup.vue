<template>
  <div class="HGroup">
    <slot></slot>
  </div>
</template>
<script>
export default {
  props: {
    'hasIcon': {
      default: true
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
