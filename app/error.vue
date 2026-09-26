<script setup lang="ts">
import type { NuxtError } from '#app'

defineProps<{
  error: NuxtError
}>()

useSeoMeta({
  title: 'Link not found — dae.ng',
  robots: 'noindex',
})
</script>

<template>
  <NuxtLayout name="default">
    <main class="flex min-h-[70dvh] flex-1 items-center px-6 py-16">
      <div class="mx-auto w-full max-w-2xl">
        <p class="font-mono text-sm text-muted-foreground">{{ error.statusCode || 404 }}</p>
        <h1 class="mt-5 text-4xl font-semibold tracking-tight sm:text-6xl">
          This short link<br>
          doesn’t exist.
        </h1>
        <p class="mt-6 max-w-lg text-base leading-7 text-muted-foreground sm:text-lg">
          The link may have changed, expired, or been mistyped.
        </p>
        <div class="mt-10 flex flex-wrap gap-x-6 gap-y-3 text-sm">
          <NuxtLink class="underline underline-offset-4 hover:no-underline" to="/">Go to dae.ng</NuxtLink>
          <a class="underline underline-offset-4 hover:no-underline" href="https://feisal.id">Visit portfolio</a>
        </div>
      </div>
    </main>
  </NuxtLayout>
</template>
