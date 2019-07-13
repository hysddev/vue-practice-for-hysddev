<template>
  <div class="header-user-menu-button" :class="isShowPanel ? 'is-open' : ''">
    <div class="header-user-menu-button__image"><img :src="image" :alt="alt"></div>
    <span class="fa fa-fw fa-caret-down ml-1"></span>
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator'

@Component
export default class HeaderUserMenuButton extends Vue {
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
  @Prop() private isShowPanel: boolean = false;
}
</script>

<style scoped lang="scss">
.header-user-menu-button {
  display: flex;
  align-items: center;
  position: relative;
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
  &__image {
    display: flex;
    overflow: hidden;
    border-radius: .2em;
    width: 32px;
    height: 32px;
    flex-shrink: 0;
    overflow: hidden;
  }
}
</style>
