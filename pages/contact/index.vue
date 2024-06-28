<script setup lang="ts">
const icons = {
  gmail: 'simple-icons:gmail',
  whatsapp: 'simple-icons:whatsapp',
  linkedin: 'simple-icons:linkedin',
};

const socials = {
  gmail: {
    url: 'mailto:muhammadzahidabdillah@gmail.com',
    text: 'muhammadzahidabdillah@gmail.com',
  },
  whatsapp: {
    url: 'https://wa.me/+6281934043331',
    text: '+62 819 3404 3331',
  },
  linkedin: {
    url: 'https://www.linkedin.com/in/zahidabdillah',
    text: 'zahidabdillah',
  },
};
</script>

<template>
  <div>
    <PageTitle>Contact Me</PageTitle>
    <div class="rounded-lg bg-white/20 p-6 ring ring-dark/10 dark:(bg-white/10 ring-white/30)">
      <ul class="flex flex-col gap-4 ml-2">
        <li v-for="(social, key) in socials" :key="key">
          <a :href="social.url" target="_blank" :title="key"
             class="text-md group inline-flex items-center rounded-lg bg-black/2 px-4 py-3 text-black font-medium ring ring-black/30 hover:ring-black/70 transition duration-200 space-x-3 dark:(bg-white/10 text-white ring-white/30 hover:ring-white/70)">
            <Icon :name="icons[key]" />
          </a>
          <span class="ml-6">{{ social.text }}</span>
        </li>
      </ul>
    </div>
  </div>
</template>