<template>
  <div class="home">
    <header-logo/>
    <header-notice number="0"/>
    <header-user-menu image="https://placehold.jp/80/333333/ffffff/150x150.png?text=A" alt="user name"/>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator'
import HeaderLogo from '@/components/atoms/HeaderLogo.vue'
import HeaderNotice from '@/components/atoms/HeaderNotice.vue'
import HeaderUserMenu from '@/components/atoms/HeaderUserMenu.vue'

@Component({
  components: {
    HeaderLogo,
    HeaderNotice,
    HeaderUserMenu
  }
})

export default class Home extends Vue {}
</script>
