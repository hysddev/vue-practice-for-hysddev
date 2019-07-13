<template>
  <div class="the-header">
    <div class="the-header__inner">
      <div class="the-header__start">
        <header-logo/>
      </div>
      <div class="the-header__end">
        <header-notice number="0"/>
        <header-user-menu image="https://placehold.jp/80/333333/ffffff/150x150.png?text=A" alt="user name"/>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator'
import HeaderLogo from '@/components/atoms/HeaderLogo.vue'
import HeaderNotice from '@/components/molecules/HeaderNotice.vue'
import HeaderUserMenu from '@/components/molecules/HeaderUserMenu.vue'

@Component({
  components: {
    HeaderLogo,
    HeaderNotice,
    HeaderUserMenu
  }
})

export default class TheHeader extends Vue {}
</script>

<style scoped lang="scss">
.the-header {
  background-color: #55c500;
  color: #fff;
  padding-right: 8px;
  padding-left: 8px;
  &__inner {
    display: flex;
    align-items: center;
    justify-content: space-between;
    height: 56px;
    max-width: 1100px;
    margin-left: auto;
    margin-right: auto;
  }
  &__start {
    display: flex;
    align-items: center;
    justify-content: center;
    height: 100%;
    position: relative;
  }
  &__end {
    display: flex;
    align-items: center;
    justify-content: center;
  }
}
</style>
