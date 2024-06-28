<script lang="ts" setup>
useSeoMeta({
  title: 'About Me',
  description: 'Discover the story behind my work and who I am.',
})
</script>

<template>
  <div class="flex flex-col">
    <PageTitle>About Me</PageTitle>
    <div
      class="w-full flex flex-col justify-between rounded-lg bg-white/20 p-6 ring ring-dark/10 dark:(bg-white/10 ring-white/30)">
      <p class="text-md mb-3 md:text-lg">
        I am a highly motivated fresh graduate with a degree in Business Management, possessing a keen interest in
        digital marketing and social media marketing. My professional journey is bolstered by a certification from
        Google, demonstrating my proficiency in these dynamic fields. I excel in critical thinking, leadership, and
        adaptability, consistently approaching tasks with a meticulous and detail-oriented mindset. My diverse skill set
        and commitment to continuous learning make me a valuable asset poised to contribute effectively to any
        forward-thinking marketing team.
      </p>

      <p class="text-md md:text-lg">
        If you would like to talk to me about any business inquiries, please feel free to
        contact me or connect with me on my LinkedIn below.
      </p>

      <SocialLinks class="mt-4 justify-end" />
    </div>
  </div>
</template>
