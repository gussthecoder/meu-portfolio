<template>
  <div id="tela">
    <IndexSectionHero />
  </div>
</template>

<script setup>
definePageMeta({
  layout: 'web'
})

useHead({
  title: 'Dr. Lucas Azevedo | Transplante Capilar FUE em São Paulo',
  meta: [
    {
      name: 'description',
      content:
        'Recupere sua linha capilar com naturalidade e segurança. Avaliação personalizada com o Dr. Lucas Azevedo, especialista em transplante capilar FUE.'
    },
    { property: 'og:title', content: 'Dr. Lucas Azevedo | Transplante Capilar FUE em São Paulo' },
    {
      property: 'og:description',
      content:
        'Técnica FUE sem cicatriz linear, planejamento digital e acompanhamento médico completo para resultados naturais.'
    }
  ]
})
</script>
