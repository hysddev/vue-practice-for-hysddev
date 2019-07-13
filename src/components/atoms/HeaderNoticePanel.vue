<template>
  <div class="header-notice-panel" :class="isShowPanel ? 'is-open' : ''">
    <div class="header-notice-panel__header">
      <div><span class="fa fa-bell-o mgr-1"></span>お知らせ</div>
      <a href="#">通知設定</a>
    </div>
    <div class="header-notice-panel__main"></div>
    <div class="header-notice-panel__footer">
      <a href="#">通知一覧を見る</a>
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator'

@Component
export default class HeaderNoticePanel extends Vue {
  /**
   * Notice show state
   */
  @Prop() private isShowPanel: boolean = false;
}
</script>

<style scoped lang="scss">
.header-notice-panel {
  display: none;
  position: absolute;
  top: 50px;
  right: -30px;
  z-index: 1000;
  width: 320px;
  height: 480px;
  background-color: #fff;
  padding: 16px 0;
  border: 1px solid #ddd;
  border-radius: 3px;
  box-shadow: 0 0 8px 0 rgba(0,0,0,.15);
  &.is-open {
    display: block;
  }
  a {
    color: #333;
    text-decoration: none;
  }
  &__header{
    display: flex;
    align-items: center;
    justify-content: space-between;
    color: #333;
    font-size: 1.2rem;
    padding-right: 16px;
    padding-left: 16px;
    margin-bottom: 8px;
    span {
      margin-right: 3px;
    }
  }
  &__main {
    width: 100%;
    height: calc(100% - 40px);
  }
  &__footer {
    display: flex;
    align-items: center;
    justify-content: center;
    color: #333;
    font-size: 1.2rem;
    padding: 0 16px;
    height: 30px;
  }
}
</style>
