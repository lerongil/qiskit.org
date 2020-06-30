<template>
  <AppLink
    class="qiskit-version-info"
    url="https://github.com/Qiskit/qiskit"
    :segment="{ action: 'GitHub repository' }"
  >
    <LogoGitHub32 class="qiskit-version-info__github-icon" />
    <div class="qiskit-version-info__content">
      <p class="qiskit-version-info__version-string">
        qiskit {{ version }}
      </p>
      <p class="qiskit-version-info__release-notes">
        See
        <AppLink
          class="qiskit-version-info__release-notes-link"
          url="https://qiskit.org/documentation/release_notes.html#notable-changes"
          :segment="{ action: 'Release notes' }"
        >
          release notes
        </AppLink>
      </p>
    </div>
  </AppLink>
</template>

<script lang="ts">
import Vue from 'vue'
import { Component, Prop } from 'vue-property-decorator'
import AppLink from '~/components/ui/AppLink.vue'

@Component({
  components: { AppLink }
})
export default class extends Vue {
  @Prop({ type: String, required: true }) version!: string
}
</script>

<style lang="scss" scoped>
@import '~carbon-components/scss/globals/scss/typography';

.qiskit-version-info {
  display: flex;
  flex-direction: row;
  align-items: center;
  text-decoration: none;

  &__github-icon {
    fill: $purple-70;
    margin-right: $spacing-07;

    @include mq($from: medium, $until: large) {
      margin-right: $spacing-05;
    }

    @include mq($until: medium) {
      margin-right: $spacing-03;
    }
  }

  &__content {
    display: flex;
    flex-direction: column;
  }

  &__version-string {
    @include type-style('code-01');
    color: $white-text-01;
    text-decoration: none;
    margin-bottom: $spacing-01;
  }

  &__release-notes {
    @include type-style('code-01');
    color: $purple-50;
  }

  &__release-notes-link {
    color: currentColor;
  }
}
</style>