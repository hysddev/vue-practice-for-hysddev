<template>
  <div class="header-notice">{{ number }}</div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator'

@Component
export default class HeaderNotice extends Vue {
  @Prop() private number!: number;
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.header-notice {
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
