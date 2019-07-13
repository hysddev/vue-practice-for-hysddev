<template>
  <div class="home">
    <header-logo/>
    <header-notice-button number="0"/>
    <!-- <header-user-menu image="https://placehold.jp/80/333333/ffffff/150x150.png?text=A" alt="user name"/> -->
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator'
import HeaderLogo from '@/components/atoms/HeaderLogo.vue'
import HeaderNoticeButton from '@/components/molecules/HeaderNoticeButton.vue'
// import HeaderUserMenu from '@/components/atoms/HeaderUserMenu.vue'

@Component({
  components: {
    HeaderLogo,
    HeaderNoticeButton
    // HeaderUserMenu
  }
})

export default class Home extends Vue {}
</script>
