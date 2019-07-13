<template>
  <div class="header-notice-count">{{ number }}</div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator'

@Component
export default class HeaderNoticeCount extends Vue {
  /**
   * Notice count
   */
  @Prop() private number!: number;
}
</script>

<style scoped lang="scss">
.header-notice-count {
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
</style>
