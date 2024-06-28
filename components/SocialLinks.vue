<script lang="ts" setup>
const { socials } = useAppConfig()

const icons = {
  github: 'simple-icons:github',
  x: 'simple-icons:x',
  linkedin: 'simple-icons:linkedin',
}

function icon(name: keyof typeof socials) {
  return icons[name]
}
</script>

<template>
  <ul class="flex flex-row space-x-3">
    <li
      v-for="(url, key) in socials"
      :key="key"
    >
      <a
        class="text-md group inline-flex items-center rounded-lg bg-black/2 px-4 py-3 text-black font-medium ring ring-black/30 hover:ring-black/70 transition duration-200 space-x-3 dark:(bg-white/10 text-white ring-white/30 hover:ring-white/70)"
        target="_blank"
        :href="url"
        :title="key"
      >
        <Icon
          :name="icon(key)"
        />
      </a>
    </li>
  </ul>
</template>
