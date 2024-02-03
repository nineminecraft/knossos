<template>
  <div class="normal-page">
    <div class="normal-page__sidebar">
      <aside class="universal-card">
        <h1>Legal</h1>
        <NavStack>
          <NavStackItem style="text-decoration: wavy underline; text-decoration-color: var(--color-brand);"
            link="/legal/about" label="About nineMinecraft">
            <HeartIcon />
          </NavStackItem>
        </NavStack>
      </aside>
    </div>
    <div class="normal-page__content">
      <NuxtPage class="universal-card" :route="route" />
    </div>
  </div>
</template>

<script setup>
import {
  InfoIcon,
  HeartHandshakeIcon,
  LockIcon,
  ScaleIcon,
  ShieldIcon,
  CurrencyIcon,
  CopyrightIcon,
  HeartIcon,
} from 'omorphia'
import NavStack from '~/components/ui/NavStack.vue'
import NavStackItem from '~/components/ui/NavStackItem.vue'

const route = useRoute()
</script>

<style lang="scss" scoped>
.normal-page__content :deep(a) {
  color: var(--color-link);
  text-decoration: underline;

  &:focus-visible,
  &:hover {
    color: var(--color-link-hover);
  }

  &:active {
    color: var(--color-link-active);
  }
}
</style>
