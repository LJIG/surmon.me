<script lang="ts" setup>
  import { useEnhancer } from '/@/app/enhancer'
  const { isDarkTheme } = useEnhancer()
</script>

<template>
  <div id="background">
    <div class="image" :class="{ dark: isDarkTheme }"></div>
  </div>
</template>

<style lang="scss" scoped>
  @import 'src/styles/variables.scss';
  @import 'src/styles/mixins.scss';

  #background {
    position: fixed;
    width: 100%;
    height: 100%;
    top: 0;
    left: 0;
    z-index: $z-index-underground;
    background-color: $body-bg;

    .image {
      position: absolute;
      width: 100%;
      height: 100%;
      opacity: 0.3;
      background: url('/images/background.png');

      &.dark {
        opacity: 0.2;
      }
    }
  }
</style>
