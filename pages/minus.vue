<template>
  <div
    style="
      text-align: center;
      padding: 8rem;
      display: flex;
      flex-direction: column;
      gap: 0.5rem;
      align-items: center;
      padding-top: 4rem;
      padding-bottom: 4rem;
      background: rgb(255, 18, 94);
      background: linear-gradient(0deg, rgba(255, 18, 94, 0.25) 0%, rgba(0, 0, 0, 1) 200%);
    "
  >
    <MinusLogo style="height: 2rem" />
    <h1 style="font-size: 4rem; margin-top: 0rem">Get the same experience</h1>
    Subscribe to nineMinusCraft to get the exact same experience, support nineMinecraft's
    development, and get an exclusive profile badge! One tenth of your subscription goes directly to
    nineMinecraft creators. Cancelling is not available at this time.
    <h1 style="color: var(--color-brand)">$1,000/mo</h1>
    Or save 500% with annual billing!
    <Button style="width: 10rem; height: 4rem; font-weight: bold; font-size: 1.5rem" color="red"
      >Subscribe</Button
    >
  </div>
</template>
<script setup>
import { Button } from 'omorphia'
import MinusLogo from '~/components/brand/MinusLogo.vue'
</script>
