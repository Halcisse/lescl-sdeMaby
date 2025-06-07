<template>
  <div class="pt-24 p-4">
    <h2 class="text-2xl font-semibold text-center mb-6">Nos Villas</h2>
    <div class="relative overflow-hidden w-full max-w-4xl mx-auto">
      <div ref="track" class="flex transition-transform duration-500">
        <img v-for="(img, i) in images" :key="i" :src="img" class="w-full shrink-0 rounded-xl" />
      </div>
      <button @click="prev" class="absolute top-1/2 left-2">❮</button>
      <button @click="next" class="absolute top-1/2 right-2">❯</button>
    </div>
  </div>
</template>

<script setup>
const images = ['/images/villa1.jpg', '/images/villa2.jpg', '/images/villa3.jpg']
const track = ref(null)
let index = 0

const update = () => {
  const width = track.value.children[0].clientWidth
  track.value.style.transform = `translateX(-${index * width}px)`
}

const next = () => { index = (index + 1) % images.length; update() }
const prev = () => { index = (index - 1 + images.length) % images.length; update() }

onMounted(() => window.addEventListener('resize', update))
</script>
