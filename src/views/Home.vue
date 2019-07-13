<template>
  <div class="home">
    <the-header/>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator'
import TheHeader from '@/components/organisms/TheHeader.vue'

@Component({
  components: {
    TheHeader
  }
})

export default class Home extends Vue {}
</script>
