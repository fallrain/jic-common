<template>
  <div class="DepartmentDetailItem">
    <p class="DepartmentDetailItem-title">{{title}}</p>
    <slot></slot>
  </div>
</template>
<script>
export default {
  props: ['title']
};
</script>
<style>

</style>
