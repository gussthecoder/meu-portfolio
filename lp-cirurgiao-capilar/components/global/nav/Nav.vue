<template>
  <nav :class="['nav-site', { sticky: navbarSticky }]">
    <div class="nav-container">
      <a href="#inicio" class="marca">
        <span class="marca-selo">LA</span>
        <span class="marca-texto">Dr. Lucas Azevedo</span>
      </a>

      <div class="links">
        <a href="#diferenciais">Diferenciais</a>
        <a href="#servicos">Protocolo</a>
        <a href="#depoimentos">Depoimentos</a>
      </div>

      <a href="#agendar" class="cta">Agendar Avaliação</a>
    </div>
  </nav>
</template>

<script setup>
const navbarSticky = ref(false)

const atualizarNavbar = () => {
  if (!process.client) return
  navbarSticky.value = window.scrollY > 24
}

onMounted(() => {
  atualizarNavbar()
  window.addEventListener('scroll', atualizarNavbar, { passive: true })
})

onBeforeUnmount(() => {
  if (!process.client) return
  window.removeEventListener('scroll', atualizarNavbar)
})
</script>

<style scoped lang="sass">
nav.nav-site
  position: sticky
  top: 0
  z-index: 60
  width: 100%
  padding: 0
  background: transparent
  transition: background .22s ease, box-shadow .22s ease, backdrop-filter .22s ease

.nav-container
  width: min(1280px, calc(100% - 3rem))
  min-height: 84px
  margin: 0 auto
  display: flex
  align-items: center
  justify-content: space-between
  gap: 1.4rem
  transition: min-height .22s ease, width .22s ease, padding .22s ease, background .22s ease, box-shadow .22s ease

.marca
  display: inline-flex
  align-items: center
  gap: .8rem
  color: #08283c

.marca-selo
  width: 2.35rem
  height: 2.35rem
  display: grid
  place-items: center
  border-radius: 50%
  background: linear-gradient(180deg, #0c4f68 0%, #08283c 100%)
  color: #f7fbfd
  font-family: Georgia, 'Times New Roman', serif
  font-size: 1rem

.marca-texto
  font-family: Georgia, 'Times New Roman', serif
  font-size: var(--f4)
  letter-spacing: -0.03em

.links
  display: flex
  align-items: center
  gap: 2rem

.links a
  color: #5b7381
  font-size: var(--f2)
  transition: color .2s ease

.links a:hover
  color: #0d4f69

.cta
  min-height: 46px
  padding: 0 1.25rem
  display: inline-flex
  align-items: center
  justify-content: center
  border-radius: 999px
  background: #08283c
  color: #ffffff
  font-family: var(--bold)
  box-shadow: 0 12px 24px rgba(8, 40, 60, 0.12)
  transition: transform .2s ease, box-shadow .2s ease

.cta:hover
  transform: translateY(-1px)

nav.nav-site.sticky
  background: transparent
  backdrop-filter: none
  box-shadow: none

nav.nav-site.sticky .nav-container
  min-height: 72px
  width: min(1220px, calc(100% - 4rem))
  margin-top: .65rem
  padding: 0 1.1rem
  border-radius: 999px
  background: rgba(247, 250, 251, 0.78)
  backdrop-filter: blur(14px)
  box-shadow: 0 10px 28px rgba(8, 40, 60, 0.08)

nav.nav-site.sticky .links a
  color: #49616f

nav.nav-site.sticky .cta
  box-shadow: 0 10px 22px rgba(8, 40, 60, 0.1)

@media screen and (max-width: 1000px)
  .nav-container
    width: min(1280px, calc(100% - 1.4rem))
    min-height: 72px

  .links
    display: none

  .marca-texto
    font-size: var(--f2)

  .cta
    min-height: 40px
    padding: 0 .95rem
    font-size: var(--f0)

  nav.nav-site.sticky .nav-container
    min-height: 64px
    width: min(1280px, calc(100% - 1.2rem))
    margin-top: .45rem
    padding: 0 .8rem
</style>

