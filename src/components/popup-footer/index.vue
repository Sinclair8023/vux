<template>
  <div class="vux-popup-footer" :class="showBottomBorder ? 'vux-1px-b' : ''">
    <div class="vux-popup-footer-left vux-1px" @click="$emit('on-click-left')">
      <slot name="left-text">{{ leftText }}</slot>
    </div>
    <div class="vux-popup-footer-right vux-1px" @click="$emit('on-click-right')">
      <slot name="right-text">{{ rightText }}</slot>
    </div>
  </div>
</template>

<script>
export default {
  name: 'popup-footer',
  props: {
    leftText: String,
    rightText: String,
    title: String,
    showBottomBorder: {
      type: Boolean,
      default: true
    }
  }
}
</script>

<style lang="less">
@import '../../styles/1px.less';
@import '../../styles/variable.less';

.vux-popup-footer {
  display: flex;
  align-items: stretch;
  height: @popup-footer-height;
  line-height: @popup-footer-height;
  font-size: @popup-footer-font-size;
  background-color: @popup-footer-bg-color;
}
.vux-popup-footer-left {
  flex:1;
  line-height: @popup-footer-height;
  text-align: center;
  color: @popup-footer-left-text-color;
}
.vux-popup-footer-right {
  flex:1;
  text-align: center;
  border-left: none;
  line-height: @popup-footer-height;
  color: @popup-footer-right-text-color;
}
</style>
