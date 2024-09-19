<script lang="ts" setup>
const page = ref(1)
const el = ref<HTMLElement>()
const pageLimit = computed(() => page.value * 12)

const { data: articles } = await useAsyncData('articles', () =>
  queryContent('/articles')
    .sort({
      title: 1,
    })
    .limit(pageLimit.value)
    .find())
</script>

<template>
  <div class="flex flex-col">
    <h1 class="font-bold text-3xl md:text-4xl mb-6">Articles</h1>
    <div
      v-if="articles?.length"
      ref="el"
      class="grid-cols grid gap-4 sm:grid-cols-2"
    >
      <ProjectCard
        v-for="article in articles"
        :key="article.name"
        :project="article"
      />
    </div>
  </div>
</template>

<style lang="postcss">
.horizontal-snap {
  display: grid;
  grid-auto-flow: column;
  overflow-y: hidden;
  overscroll-behavior-x: contain;
  scroll-snap-type: x mandatory;
}

.horizontal-snap > .card {
  scroll-snap-align: center;
}
</style>
