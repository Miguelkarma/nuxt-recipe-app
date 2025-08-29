<script lang="ts" setup>
import { type RecipeResponse } from "@/types/types";
const { data, error } = await useFetch<RecipeResponse>(
  "https://dummyjson.com/recipes?limit=12"
);
</script>
<template>
  <main>
    <section class="bg-[#f1f1f1]">
      <div
        class="container flex flex-col lg:flex-row items-center py-20 gap-10"
      >
        <div class="flex-1 order-2 lg:order-1 text-center lg:text-left">
          <h1 class="text-4xl lg:text-6xl font-extrabold mb-6 text-balance">
            Master the Kitchen with Ease: Unleash Your Inner Chef Today!
          </h1>
          <p class="text-xl lg:text-2xl mb-8 text-balance">
            Discover recipes helping you to find the easiest way to cook.
          </p>

          <button
            class="px-4 py-2 text-white self-start bg-gray-800 rounded-md text-lg cursor-pointer"
          >
            browse
          </button>
        </div>
        <div class="flex-1 order-1 lg:order-2">
          <NuxtImg
            sizes="xs:100vw sm:667px"
            src="/nuxt-course-hero.png"
            format="webp"
            densities="x1"
            alt=""
          />
        </div>
      </div>
    </section>
    <section class="container py-20">
      <h1 class="text-5xl mb-2">Ricipes</h1>
      <p class="text-xl mb-8">Check out our most popular recipes!</p>
      <div class="grid grid-cols-3 gap-x-4 gap-y-8">
        <div v-for="recipe in data?.recipes" class="shadow rounded-md">
          <NuxtImg
            :src="recipe.image"
            sizes="xs:100wv sm:50vw lg:500px"
            alt=""
            class="rounded-t-md"
            format="webp"
            densities="x1"
          />
          <div class="flex flex-col py-6 px-4">
            <p class="text-2xl font-semibold mb-2">{{ recipe.name }}</p>
            <div class="font-normal w-full bg-white/80 flex gap-8 text-xl mb-4">
              <div class="flex items-center gap-1">
                <Icon
                  name="mdi:clock-time-eight-outline"
                  width="1.2em"
                  height="1.2em"
                  style="color: #f79f1a"
                />
                <span>{{ recipe.cookTimeMinutes }}</span>
              </div>
              <div class="flex items-center gap-1">
                <Icon
                  name="mdi:fire"
                  width="1.2em"
                  height="1.2em"
                  style="color: #f79f1a"
                />
                <span>{{ recipe.caloriesPerServing }}</span>
              </div>
              <div class="flex items-center gap-1">
                <Icon
                  name="mdi:star"
                  width="1.2em"
                  height="1.2em"
                  style="color: #f79f1a"
                />
                <span>{{ recipe.rating }} ({{ recipe.reviewCount }})</span>
              </div>
            </div>
            <NuxtLink
              :to="`/recipes/${recipe.id}`"
              class="px-4 py-2 text-white self-start bg-gray-800 rounded-md text-lg cursor-pointer"
            >
              <span>View Recipe</span>
            </NuxtLink>
          </div>
        </div>
      </div>
    </section>
  </main>
</template>
