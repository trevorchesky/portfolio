<script lang="ts" setup>
const page = ref(1)
const el = ref<HTMLElement>()
const pageLimit = computed(() => page.value * 12)

const { data: contents } = await useAsyncData('contents', () =>
  queryContent('/contents')
    .sort({
      title: 1,
    })
    .limit(pageLimit.value)
    .find())
</script>

<template>
  <div class="flex flex-col">
    <h1 class="font-bold text-3xl md:text-4xl mb-6">Social Media Contents</h1>
    <div
      v-if="contents?.length"
      ref="el"
      class="grid-cols grid gap-4 sm:grid-cols-2"
    >
      <ProjectCard
        v-for="content in contents"
        :key="content.name"
        :project="content"
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
