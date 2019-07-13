<template>
  <div class="home">
    <header-logo/>
    <header-notice number="0"/>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator'
import HeaderLogo from '@/components/atoms/HeaderLogo.vue'
import HeaderNotice from '@/components/atoms/HeaderNotice.vue'

@Component({
  components: {
    HeaderLogo,
    HeaderNotice
  }
})

export default class Home extends Vue {}
</script>
