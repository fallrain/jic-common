<template>
  <div class="HFeedback clip">
    <div class="HFeedback-time">{{time}}</div>
    <i class="iconfont icon-qubiezhen"></i>
    <div class="HFeedback-quest-body">
      <label class="HFeedback-quest">问题描述:</label>
      <p class="HFeedback-answer">{{question}}</p>
    </div>
    <div class="HFeedback-quest-body">
      <label class="HFeedback-quest">问题回复:</label>
      <p class="HFeedback-answer">{{anwser}}</p>
    </div>
  </div>
</template>
<script>
export default {
  props: {
    question: {
      type: String
    },
    anwser: {
      type: String
    },
    time: {
      type: String
    }
  }
};
</script>
<style>

</style>
