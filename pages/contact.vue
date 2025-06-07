<template>
  <div class="pt-24 max-w-xl mx-auto p-4">
    <h2 class="text-2xl mb-4 text-center">Contactez-nous</h2>
    <form action="https://formspree.io/f/yourformid" method="POST" class="flex flex-col gap-4">
      <input type="text" name="name" placeholder="Nom" required class="border p-2 rounded">
      <input type="email" name="email" placeholder="Email" required class="border p-2 rounded">
      <textarea name="message" placeholder="Message" required class="border p-2 rounded"></textarea>
      <div class="g-recaptcha" data-sitekey="votre_clé_site"></div>
      <button type="submit" class="bg-blue-500 text-white p-2 rounded">Envoyer</button>
    </form>
  </div>
</template>

<script setup>
onMounted(() => {
  const script = document.createElement('script')
  script.src = 'https://www.google.com/recaptcha/api.js'
  script.async = true
  document.body.appendChild(script)
})
</script>
