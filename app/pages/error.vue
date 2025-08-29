<script setup lang="ts">
import type { NuxtError } from "#app";

const { error } = defineProps<{ error: NuxtError }>();

const handleError = () => clearError({ redirect: "/" });
</script>

<template>
  <section class="flex min-h-screen flex-col items-center justify-center">
    <h1 class="mb-2 text-9xl font-bold">
      {{ error.statusCode }}
    </h1>
    <p class="mb-10 text-xl sm:text-3xl">
      {{ error.statusMessage }}
    </p>

    <UButton @click="handleError">Go home</UButton>
  </section>
</template>
