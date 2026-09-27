<script setup lang="ts">
import type { NuxtError } from '#app'

const props = defineProps<{
  error: NuxtError
}>()

const statusCode = computed(() => props.error.statusCode || 500)

const errorContent = computed(() => {
  if (statusCode.value === 404) {
    return {
      title: 'Link not found — dae.ng',
      heading: 'This short link doesn’t exist.',
      description: 'The link may have changed, expired, or been mistyped.',
    }
  }

  if (statusCode.value === 401 || statusCode.value === 403) {
    return {
      title: 'Access denied — dae.ng',
      heading: 'You can’t access this page.',
      description: 'Check that you’re signed in with the right account and try again.',
    }
  }

  if (statusCode.value >= 500) {
    return {
      title: 'Server error — dae.ng',
      heading: 'dae.ng is having trouble.',
      description: 'This is a temporary server problem. Please try again in a moment.',
    }
  }

  return {
    title: 'Something went wrong — dae.ng',
    heading: 'Something went wrong.',
    description: 'An unexpected error interrupted this page. Reload it and try again.',
  }
})

useSeoMeta({
  title: () => errorContent.value.title,
  description: () => errorContent.value.description,
  ogTitle: () => errorContent.value.title,
  ogDescription: () => errorContent.value.description,
  twitterTitle: () => errorContent.value.title,
  twitterDescription: () => errorContent.value.description,
  robots: 'noindex',
})
</script>

<template>
  <NuxtLayout name="default">
    <main class="flex min-h-[70dvh] flex-1 items-center px-6 py-16">
      <div class="mx-auto w-full max-w-2xl">
        <p class="font-mono text-sm text-muted-foreground">
          {{ statusCode }}
        </p>
        <h1
          class="
            mt-5 text-4xl font-semibold tracking-tight
            sm:text-6xl
          "
        >
          {{ errorContent.heading }}
        </h1>
        <p
          class="
            mt-6 max-w-lg text-base/7 text-muted-foreground
            sm:text-lg
          "
        >
          {{ errorContent.description }}
        </p>
      </div>
    </main>
  </NuxtLayout>
</template>
