<template>
  <div>
    <div class="HNotice-item">
      <p class="HNotice-item-type">
        <i :class="['iconfont',iconTypeCls]"></i>
        <span class="HNotice-item-type-inf">{{iconTypeInf}}</span>
      </p>
      <p class="HNotice-item-detail img100per" v-if="contentHtml" v-html="content"></p>
      <p class="HNotice-item-detail" v-else>{{content}}</p>
    </div>
    <div class="HNotice-btm">
      <span class="status" :style="{'color': isRead?'#3693DA':'#FF0000'}">
        <!--<i :style="{'background': isRead?'#3693DA':'#FF0000'}"></i>{{isRead?'已读':'未读'}}-->
      </span>
      <span class="time">{{time}}</span>
    </div>
  </div>
</template>
<script>
export default {
  props: {
    iconType: {
      type: String
    },
    contentHtml: {
      type: Boolean,
      default: false
    },
    content: {
      type: String
    },
    isRead: {
      type: Boolean
    },
    time: {
      type: String
    }
  },
  data () {
    return {
    };
  },
  computed: {
    iconTypeCls () {
      const iconType = {
        urgent: 'icon-lingdang',
        'sys': 'icon-lingdang',
        'news': 'icon-diqiu-copy'
      };
      return iconType[this.iconType];
    },
    iconTypeInf () {
      const iconTypeInf = {
        urgent: '紧急通知',
        'sys': '系统通知',
        'news': '我院动态'
      };
      return iconTypeInf[this.iconType];
    }
  }
};
</script>
<style>

</style>
