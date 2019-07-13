<template>
  <div class="header-notice-button" @click="buttonClick()">
    <header-notice-count :number="number"/>
    <header-notice-panel :isShowPanel="isShowPanel"/>
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator'
import HeaderNoticeCount from '@/components/atoms/HeaderNoticeCount.vue'
import HeaderNoticePanel from '@/components/atoms/HeaderNoticePanel.vue'

@Component({
  components: {
    HeaderNoticeCount,
    HeaderNoticePanel
  }
})
export default class HeaderNoticeButton extends Vue {
  /**
   * Notice count
   */
  @Prop() private number!: number;

  /**
   * Notice show state
   */
  @Prop() private isShowPanel: boolean = false;

  /**
   * Button click handler
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
.header-notice-button {
  position: relative;
  &__button {
    display: flex;
    align-items: center;
    justify-content: center;
    width: 32px;
    height: 32px;
    background-color: #edfce2;
    color: #3f9200;
    border-radius: 4px;
    font-size: 1.4rem;
    position: relative;
    cursor: pointer;
    user-select: none;
    margin-right: 16px;
    outline: none;
  }
  &__panel {
    display: none;
    position: absolute;
    top: 40px;
    right: 0;
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
