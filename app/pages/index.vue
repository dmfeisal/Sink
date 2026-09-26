<script setup lang="ts">
useSeoMeta({
  title: 'dae.ng — Short links by Daeng M. Feisal',
  description: 'A personal short-link service by Daeng M. Feisal.',
})
</script>

<template>
  <main class="flex min-h-dvh items-center bg-background px-6 py-12 text-foreground">
    <div class="mx-auto w-full max-w-2xl">
      <p class="mb-6 font-mono text-sm text-muted-foreground">dae.ng</p>
      <h1 class="max-w-xl text-4xl font-semibold tracking-tight sm:text-6xl">
        Short links,<br>
        kept simple.
      </h1>
      <p class="mt-6 max-w-lg text-base leading-7 text-muted-foreground sm:text-lg">
        This is Daeng M. Feisal’s personal short-link domain for sharing stable,
        memorable links across work, writing, projects, and the web.
      </p>
      <nav class="mt-10 flex flex-wrap gap-x-6 gap-y-3 text-sm">
        <a class="underline underline-offset-4 hover:no-underline" href="https://feisal.id">Portfolio</a>
        <a class="underline underline-offset-4 hover:no-underline" href="/linkedin">LinkedIn</a>
        <a class="underline underline-offset-4 hover:no-underline" href="/github">GitHub</a>
      </nav>
      <p class="mt-20 text-xs text-muted-foreground">dae.ng / personal URL shortener</p>
    </div>
  </main>
</template>
