<template>
  <div class="header-user-menu" @click="buttonClick()">
    <header-user-menu-button :image="image" :alt="alt" :isShowPanel="isShowPanel"/>
    <header-user-menu-panel :isShowPanel="isShowPanel"/>
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator'
import HeaderUserMenuButton from '@/components/atoms/HeaderUserMenuButton.vue'
import HeaderUserMenuPanel from '@/components/atoms/HeaderUserMenuPanel.vue'

@Component({
  components: {
    HeaderUserMenuButton,
    HeaderUserMenuPanel
  }
})

export default class HeaderUserMenu extends Vue {
  /**
   * User image
   */
  @Prop() private image!: string;

  /**
   * User image alt
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
.header-user-menu {
  position: relative;
}
</style>
