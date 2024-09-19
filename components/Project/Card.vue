<script lang="ts" setup>
interface ProjectCardProps {
  project?: Record<string, any>
}

const props = withDefaults(defineProps<ProjectCardProps>(), {
  project: () => ({}),
})
</script>

<template>
  <div
    class="w-[350px] w-full flex flex-col rounded-lg bg-white/20 ring ring-dark/10 dark:(bg-white/10 ring-white/30) h-full"
  >
    <a
      class="h-46 overflow-hidden rounded-t-lg h-full"
      :href="props.project.link"
      target="_blank"
      @click="umTrackEvent(`project:clicked`, {
        name: props.project.name,
        title: props.project.title,
        link: props.project.link,
      })"
    >
      <NuxtImg
        class="h-full w-full object-cover object-top transition-all duration-300 hover:scale-105"
        :src="props.project.preview"
        :title="props.project.name"
        :alt="props.project.name"
        lazy
      />
    </a>
    <div class="flex flex-col flex-grow justify-between p-4">
      <div>
        <h3 v-if="props.project.title && props.project.title.trim() !== '' && isNaN(Number(props.project.title))" class="mb-2 text-2xl font-bold">
          <a :href="props.project.link" target="_blank">
            {{ props.project.title }}
          </a>
        </h3>
        <p class="text-xs md:text-sm mb-4 whitespace-pre-wrap" :title="props.project.description">
          {{ props.project.description }}
        </p>
      </div>
      <ProjectTags :tags="props.project.tags" class="mt-auto" />
    </div>
  </div>
</template>
