<template>
  <div class="header-userMenu">
    <div class="header-userMenu__button" :class="isShowPanel ? 'is-open' : ''" @click="buttonClick()">
      <div class="header-userMenu__image"><img :src="image" :alt="alt"></div>
      <span class="fa fa-fw fa-caret-down ml-1"></span>
    </div>
    <div class="header-userMenu__panel" :class="isShowPanel ? 'is-open' : ''">
      <a href="#" class="header-userMenu__item">マイページ</a>
      <div class="header-userMenu__separator"></div>
      <a href="#" class="header-userMenu__item">下書き一覧</a>
      <a href="#" class="header-userMenu__item">編集リクエスト一覧</a>
      <div class="header-userMenu__separator"></div>
      <a href="#" class="header-userMenu__item">設定</a>
      <a href="#" class="header-userMenu__item">ヘルプ</a>
      <div class="header-userMenu__separator"></div>
      <div class="header-userMenu__item">ログアウト</div>
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator'

@Component
export default class HeaderUserMenu extends Vue {
  /**
   * User image
   */
  @Prop() private image!: string;

  /**
   * User name
   */
  @Prop() private alt!: string;

  /**
   * User menu panel show state
   */
  private isShowPanel: boolean = false;

  /**
   * User menu button click handler
   */
  private buttonClick (): void {
    if (this.isShowPanel) {
      this.isShowPanel = false
    } else {
      this.isShowPanel = true
    }
  }
}
</script>

<style scoped lang="scss">
.header-userMenu {
  position: relative;
  &__button {
    display: flex;
    align-items: center;
    position: relative;
    margin-right: 16px;
    cursor: pointer;
    user-select: none;
    outline: none;
    &.is-open,
    &:hover {
      span {
        color: #fff;
      }
    }
    span {
      color: rgba(0,0,0,.3);
      font-size: 1.2rem;
    }
  }
  &__image {
    display: flex;
    overflow: hidden;
    border-radius: .2em;
    width: 32px;
    height: 32px;
    flex-shrink: 0;
    overflow: hidden;
  }
  &__panel {
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
