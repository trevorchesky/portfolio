<script lang="ts" setup>
const blobsPositions: string[] = [
  'bottom-40 left-0',
  'bottom-12 left-3/4',
  'bottom-18 left-1/2',
  'bottom-0 right-1/2',
  'top-0 -left-20',
]
const blobBgColors: string[] = [
  'bg-teal',
  'bg-purple',
  'bg-blue',
  'bg-pink',
  'bg-cyan w-full! h-12!',
]

const blobs = blobsPositions.map((position, index) => {
  return `${position} ${blobBgColors[index]}`
})
</script>

<template>
  <main
    class="min-h-[100dvh] w-full flex justify-center py-24 -z-10"
  >
    <div
      class="relative w-full max-w-screen-lg flex flex-col justify-center p-4 md:p-8 sm:p-6"
    >
      <div class="fixed top-0 z-0 h-full w-full max-w-screen-lg">
        <Blob v-for="blob in blobs" :key="blob" :class="blob" />
      </div>

      <slot />
    </div>
  </main>
</template>

<style lang="postcss" scoped>
  main {
    background-size: 40px 40px;
    background-image: url("data:image/svg+xml;charset=utf-8,%3Csvg xmlns='http://www.w3.org/2000/svg' width='20' height='20' transform='scale(3)'%3E%3Crect width='100%25' height='100%25' fill='%23fff'/%3E%3Cpath fill='none' stroke='hsla(0, 0%25, 98%25, 1)' stroke-width='.2' d='M10 0v20ZM0 10h20Z'/%3E%3C/svg%3E");
  }

  html.dark main {
    background-image: url("data:image/svg+xml;charset=utf-8,%3Csvg xmlns='http://www.w3.org/2000/svg' width='20' height='20' transform='scale(3)'%3E%3Crect width='100%25' height='100%25' fill='hsl(0, 0%25, 8.5%25)'/%3E%3Cpath fill='none' stroke='hsl(0, 0%25, 11.0%25)' stroke-width='.2' d='M10 0v20ZM0 10h20Z'/%3E%3C/svg%3E");
  }
</style>
