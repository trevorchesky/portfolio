<script lang="ts" setup>

useSeoMeta({
  title: 'Certifications',
  description: 'These are some of my certifications that I have achieved.',
})

const certifications = [
  {
    name: 'Coursera Specialization',
    title: 'Google Digital Marketing & E-Commerce Professional Certifications',
    description: 'Professional certification by Google for digital marketing.',
    link: 'https://www.coursera.org/account/accomplishments/specialization/certificate/VDV7Y3JJ6XVF',
    preview: '/cert/Coursera Digital Marketing.jpg',
    issuedBy: 'Coursera',
    tags: ['Digital Marketing', 'E-Commerce'],
  },
  {
    name: 'Mastering Skill Certificate',
    title: 'Merancang Strategi Pemasaran Digital',
    description: 'Course on designing digital marketing strategies.',
    link: 'https://www.masteringskill.com/id/certificates/eyJ1c2VyX2lkIjoiODZlMTQ1MjYtZTU4YS00ZDg5LWJkNGItNjM1OTZmODJkMmQyIiwiZW5yb2xsbWVudF9pZCI6IjBVRXpkMktmMXhuVlkwMWZDSDJnIiwiY291cnNlX2NlcnRpZmljYXRlX2lkIjo2Nzl9',
    preview: '/cert/Mastering Skill Strategi Pemasaran Digital.png',
    issuedBy: 'Mastering Skill',
    tags: ['Digital Marketing', 'Strategy'],
  },
];
</script>

<template>
  <div>
    <PageTitle>Certifications</PageTitle>
    <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
      <div v-for="(certification, index) in certifications" :key="index"
        class="flex flex-col rounded-lg bg-white/20 ring ring-dark/10 dark:(bg-white/10 ring-white/30) mb-4">
        <a class="h-46 overflow-hidden rounded-t-lg md:h-55" :href="certification.link" target="_blank" @click="umTrackEvent(`certification:clicked`, {
          name: certification.name,
          title: certification.title,
          link: certification.link,
        })">
          <NuxtImg class="h-full w-full object-cover object-top transition-all duration-300 hover:scale-105"
            :src="certification.preview" :title="certification.name" :alt="certification.name" lazy />
        </a>
        <div class="flex flex-col p-4">
          <h3 class="mb-2 text-2xl font-bold md:text-3xl">
            <a :href="certification.link" target="_blank">
              {{ certification.title }}
            </a>
          </h3>
          <p class="text-sm italic mb-1">Issued by {{ certification.issuedBy }}</p>
          <p class="text-xs md:text-sm" :title="certification.description">
            {{ certification.description }}
          </p>
          <div class="flex flex-wrap mt-2">
            <span v-for="(tag, tagIndex) in certification.tags" :key="tagIndex"
              class="mt-2 mr-2 mb-2 px-2 py-1 rounded-md bg-dark/5 px-2 py-1 text-xs font-semibold ring ring-dark/10 dark:(bg-white/10 ring-white/15)">
              {{ tag }}
            </span>
          </div>
          <a :href="certification.link" target="_blank"
            class="justify-end mt-2 flex flex-row text-lg hover:opacity-75" :title="certification.title" @click="umTrackEvent(`certification:clicked`, {
              name: certification.name,
              title: certification.title,
              link: certification.link,
            })">
            <IconCSS name="eva:external-link-fill" />
          </a>
        </div>
      </div>
    </div>
  </div>
</template>
