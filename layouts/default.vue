<template>
  <!-- tabindex is needed to allow hiding the menu in iOS Safari -->
  <div class="default-layout content-root_theme_dark" tabindex="-1">
    <header id="navigation">
      <TheBlackLivesMatterBanner
        :style="{ display: isMenuShown ? 'none' : 'block' }"
      />
      <TheMenu @changeVisibility="isMenuShown = $event === 'shown'" />
    </header>
    <nuxt />
    <PageFooter theme="light" />
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import { Component } from 'vue-property-decorator'
import TheMenu from '~/components/layouts/TheMenu/index.vue'
import TheBlackLivesMatterBanner from '~/components/layouts/banners/TheBlackLivesMatterBanner.vue'
import PageFooter from '~/components/layouts/PageFooter/index.vue'

@Component({
  components: {
    TheMenu,
    TheBlackLivesMatterBanner,
    PageFooter
  }
})
export default class DefaultLayout extends Vue {
  isMenuShown: boolean = false
}
</script>

<style lang="scss">
@import '~/assets/scss/layout.scss';
</style>
