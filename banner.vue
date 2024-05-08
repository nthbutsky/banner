<template>
  <button
    class="banner"
    type="button"
    @click="isModalVisible = true"
  >
    <div
      class="banner__content"
      :class="{
        'banner__content_wide': isWide
      }"
    >
      <div
        class="banner__image banner__image_left"
        :class="{
          'banner__image_left-wide': isWide
        }"
      />

      <div class="banner__info">
        <h2 class="banner__headline">
          {{ $t('banner.headline') }}
        </h2>

        <div class="banner__cta">
          {{ $t('banner.cta') }}
        </div>
      </div>

      <div
        class="banner__image banner__image_right"
        :class="{
          'banner__image_right-wide': isWide
        }"
      />

      <img
        class="banner__logo"
        src="@/asset/image/logo.svg"
        :alt="$t('banner.logoAlt')"
      >

      <div class="banner__bubble">
        {{ $t('banner.bubble') }}
      </div>
    </div>
  </button>

  <modal
    :is-visible="isModalVisible"
    @hide="isModalVisible = false"
  />
</template>

<script lang="ts" setup>
import {
  ref,
} from 'vue';
import Modal from '@/component/modal/modal.vue';

withDefaults(defineProps<{
  isWide?: boolean;
}>(), {
  isWide: false,
});

const isModalVisible = ref(false);
</script>

<style lang="scss" scoped>
@use './banner.scss';
</style>
