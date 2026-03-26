<template>
  <footer class="footer-site">
    <div class="footer-container">
      <div class="brand">
        <span class="brand-badge">LA</span>
        <div>
          <p class="nome">Dr. Lucas Azevedo | CRM 123456-SP</p>
          <p class="info">Rua Oscar Freire, 890 - Jardins, São Paulo/SP</p>
        </div>
      </div>

      <div class="meta">
        <p class="info">Atendimento com hora marcada | (11) 99999-0000</p>
        <p class="copy">© {{ anoAtual }} Clínica Azevedo. Todos os direitos reservados.</p>
      </div>
    </div>
  </footer>
</template>

<script setup>
const anoAtual = new Date().getFullYear()
</script>

<style scoped lang="sass">
footer.footer-site
  width: 100%
  display: flex
  justify-content: center
  padding: 2.6rem 1rem 3rem
  background: #ffffff
  border-top: 1px solid rgba(10, 49, 71, 0.08)

.footer-container
  width: min(1180px, 100%)
  display: flex
  align-items: center
  justify-content: space-between
  gap: 1.5rem

.brand
  display: flex
  align-items: center
  gap: .9rem

.brand-badge
  width: 2.7rem
  height: 2.7rem
  display: grid
  place-items: center
  border-radius: 50%
  background: linear-gradient(180deg, #0c4f68 0%, #08283c 100%)
  color: #f7fbfd
  font-family: Georgia, 'Times New Roman', serif

.nome
  color: #08283c
  font-family: Georgia, 'Times New Roman', serif
  font-size: var(--f3)
  letter-spacing: -0.02em

.info
  margin-top: .2rem
  color: #69808d
  font-size: var(--f1)

.meta
  text-align: right

.copy
  margin-top: .4rem
  color: #96a8b2
  font-size: var(--f0)

@media screen and (max-width: 1000px)
  .footer-container
    flex-direction: column
    align-items: flex-start

  .meta
    text-align: left
</style>

