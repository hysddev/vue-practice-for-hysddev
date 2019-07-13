<template>
  <div class="header-notice" @click="buttonClick()">
    <header-notice-button :number="number"/>
    <header-notice-panel :isShowPanel="isShowPanel"/>
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator'
import HeaderNoticeButton from '@/components/atoms/HeaderNoticeButton.vue'
import HeaderNoticePanel from '@/components/atoms/HeaderNoticePanel.vue'

@Component({
  components: {
    HeaderNoticeButton,
    HeaderNoticePanel
  }
})
export default class HeaderNotice extends Vue {
  /**
   * Notice count
   */
  @Prop() private number!: number;

  /**
   * Notice show state
   */
  private isShowPanel: boolean = false;

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
.header-notice {
  position: relative;
}
</style>
