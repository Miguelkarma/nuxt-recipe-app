<script lang="ts" setup></script>

<template>
  <div>
    <header class="py-4 border-b">
      <nav class="flex container items-center">
        <nuxt-link to="/" class="flex gap-1 items-center">
          <Icon name="lucide:cooking-pot" class="text-xl" />
          <span class="text-3xl font-bold ml-1">Ricipe</span>
        </nuxt-link>
        <ul class="flex gap-6 ml-auto text-xl font-bold capitalize">
          <li>
            <nuxt-link to="/">Home</nuxt-link>
          </li>
          <li>
            <nuxt-link to="/about">About</nuxt-link>
          </li>
        </ul>
      </nav>
    </header>
  </div>
</template>
