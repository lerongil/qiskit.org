<template>
  <article
    class="the-features"
  >
    <div
      class="
        the-features__container
        copy__util
        copy__util_vertical-spacer
      "
    >
      <h2 class="copy__title">
        What can Qiskit do
      </h2>
      <p class="copy__paragraph copy__paragraph_importance_outstanding">
        Qiskit accelerates the development of quantum applications by
        providing the complete set of tools needed for interacting with
        quantum systems and simulators.
      </p>
      <TheFeatureMosaic class="the-features__mosaic" />
      <LandingCta
        url="/overview"
        kind="secondary"
        @click="$trackClickEvent({
          action: 'Overview'
        })"
      >
        Full Overview
      </LandingCta>
    </div>
  </article>
</template>

<script lang="ts">
import Vue from 'vue'

import { Component } from 'vue-property-decorator'
import TheFeatureMosaic from '~/components/landing/TheFeatures/TheFeatureMosaic.vue'
import LandingCta from '~/components/landing/LandingCta.vue'

@Component({
  components: { TheFeatureMosaic, LandingCta }
})
export default class TheFeatures extends Vue { }
</script>

<style lang="scss">
@import '~carbon-components/scss/globals/scss/typography';

.the-features {
  @include responsive-grid-bg-strip('/images/grid/grid-mosaic.svg', 112rem, auto, 16rem);

  &__container {
    @include contained();
  }

  &__mosaic {
    margin-top: $layout-01;
    margin-bottom: $layout-03;

    @include mq($from: medium, $until: large) {
      margin-bottom: $layout-01;
    }

    @include mq($until: medium) {
      margin-bottom: $layout-01;
    }
  }
}
</style>
