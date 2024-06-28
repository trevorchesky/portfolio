<script lang="ts" setup>
useSeoMeta({
  title: 'Home',
})

const profile = {
  name: 'Muhammad Zahid Abdillah',
  tags: ['#Social Media Marketing', '#Digital Marketing', '#Copywriting'],
};

useSeoMeta({
  title: 'Home',
});
</script>

<template>
  <div class="flex flex-col">
    <div class="flex flex-col gap-2 md:flex-row md:items-center">
      <NuxtLink class="block w-30 md:min-w-32" to="/cv zahid.pdf" target="_blank"
        @click="umTrackEvent('home:btn:clicked', { name: 'resume' })">
        <NuxtImg class="rounded-lg ring ring-black/20 hover:ring-black/70 transition duration-200 w-30 dark:(ring-white/20 hover:ring-white/70)" src="/profile_image.webp"
          alt="Profile Picture" lazy />
      </NuxtLink>
      <div>
        <h1 class="mt-4 mb-2 md:ml-4 text-4xl font-extrabold font-sans md:mb-3 sm:text-5xl">
          {{ profile.name }}
        </h1>
        <div class="flex flex-wrap mt-2">
          <span v-for="(tag, tagIndex) in profile.tags" :key="tagIndex"
            class="mt-2 mr-2 mb-2 md:ml-4 px-2 py-1 rounded-md bg-dark/5 px-2 py-1 text-xs font-semibold ring ring-dark/10 dark:(bg-white/10 ring-white/15)">
            {{ tag }}
          </span>
        </div>
      </div>
    </div>

    <div class="mt-6 flex flex-col justify-between gap-5 md:flex-row md:items-center md:gap-0">
      <div class="flex flex-row space-x-5">
        <NuxtLink
          class="text-md group inline-flex items-center rounded-lg bg-black/2 px-3 py-2 text-black font-medium ring ring-black/30 hover:ring-black/70 transition duration-200 space-x-3 dark:(bg-white/10 text-white ring-white/30 hover:ring-white/70)"
          to="/cv zahid.pdf" target="_blank" @click="umTrackEvent('home:btn:clicked', { name: 'resume' })">
          CV
        </NuxtLink>
        <NuxtLink
          class="text-md group inline-flex items-center rounded-lg bg-black/2 px-3 py-2 text-black font-medium ring ring-black/30 hover:ring-black/70 transition duration-200 space-x-3 dark:(bg-white/10 text-white ring-white/30 hover:ring-white/70)"
          to="/about" @click="umTrackEvent('home:btn:clicked', { name: 'about-me' })">
          About Me
        </NuxtLink>
        <NuxtLink
          class="text-md group inline-flex items-center rounded-lg bg-black/2 px-3 py-2 text-black font-medium ring ring-black/30 hover:ring-black/70 transition duration-200 space-x-3 dark:(bg-white/10 text-white ring-white/30 hover:ring-white/70)"
          to="/projects" @click="umTrackEvent('home:btn:clicked', { name: 'my-projects' })">
          Projects
        </NuxtLink>
        <div class="md:hidden">
          <SocialLinks />
        </div>
      </div>

      <div class="hidden md:block">
        <SocialLinks />
      </div>
    </div>
  </div>
</template>