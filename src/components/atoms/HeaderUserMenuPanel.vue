<template>
  <div class="header-user-menu-panel" :class="isShowPanel ? 'is-open' : ''">
    <a href="#" class="header-user-menu-panel__item">マイページ</a>
    <div class="header-user-menu-panel__separator"></div>
    <a href="#" class="header-user-menu-panel__item">下書き一覧</a>
    <a href="#" class="header-user-menu-panel__item">編集リクエスト一覧</a>
    <div class="header-user-menu-panel__separator"></div>
    <a href="#" class="header-user-menu-panel__item">設定</a>
    <a href="#" class="header-user-menu-panel__item">ヘルプ</a>
    <div class="header-user-menu-panel__separator"></div>
    <div class="header-user-menu-panel__item">ログアウト</div>
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator'

@Component
export default class HeaderUserMenuPanel extends Vue {
  /**
   * User menu panel show state
   */
  @Prop() private isShowPanel: boolean = false;
}
</script>

<style scoped lang="scss">
.header-user-menu-panel {
  display: none;
  position: absolute;
  top: 52px;
  z-index: 20;
  width: 200px;
  background-color: #fff;
  padding: 4px 0;
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
  &__item{
    display: block;
    font-size: 1.2rem;
    font-weight: 400;
    padding: 12px 16px;
    color: #555;
    cursor: pointer;
    &:hover {
      background-color: #eee;
    }
  }
  &__separator {
    width: 100%;
    height: 1px;
    margin: 4px 0;
    background-color: #ddd;
  }
}
</style>
