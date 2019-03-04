<!--详情主页头部-->
<template>
  <div class="DeparntmentDetailHead">
    <i
      v-if="hasLike"
      :class="['iconfont', 'icon-xingzhuang39','DeparntmentDetailHead-like',isLike && 'active']"
      @click="like"
    ></i>
    <div class="DeparntmentDetailHead-topBg">
      <div class="pseudo-clear DeparntmentDetailHead-inf-par">
        <img
          class="DeparntmentDetailHead-headPorlrait"
          :src="imgSrc"
        >
        <div class="DeparntmentDetailHead-inf">
          <div>
            <span class="DeparntmentDetailHead-inf-title">{{name}}</span>
            <span class="DeparntmentDetailHead-inf-titleType">{{titleType}}</span>
          </div>
          <div class="DeparntmentDetailHead-time">
            <i v-if="isTime" class="iconfont icon-naozhong"></i>
            <ol class="DeparntmentDetailHead-time-inf">
              <li
                v-for="(item ,i) in detail"
                :key="i"
              >
                <a :href="item.isTel?'tel:'+item.tel:'javascript:;'">
                  <span v-if="item.isHtml" v-html="item.cnt"></span>
                  <span v-else>{{item.cnt}}</span>
                  <i
                    v-if="item.icon"
                    :class="['iconfont',item.icon]">
                  </i>
                </a>
              </li>
            </ol>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  props: {
    'name': {
      default: ''
    },
    'imgSrc': {
      default: ''
    },
    'hasLike': {
      default: false
    },
    'isTime': {
      default: false
    },
    'titleType': {
      default: ''
    },
    'detail': {
      default: ''
    },
    likeClick: {
      type: Function
    },
    isLike: {
      default: false
    }
  },
  methods: {
    like () {
      this.likeClick && this.likeClick();
    }
  }
};
</script>
<style>

</style>
