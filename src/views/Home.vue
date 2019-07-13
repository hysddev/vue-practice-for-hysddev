<template>
  <div class="home">
    <header-logo/>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator'
import HeaderLogo from '@/components/atoms/HeaderLogo.vue'

@Component({
  components: {
    HeaderLogo
  }
})
export default class Home extends Vue {}
</script>
