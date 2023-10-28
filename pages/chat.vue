<template>
    <div class="inbox-section">
        <h1 class="inbox-tittle">Minhas mensagens</h1>

        <Card />
    </div>
</template>

<script>
import Card from '~/components/cards/Card.vue'

export default {
    name: 'chat',
    components: {
        Card,
    }
}
</script>

<style scoped lang="sass">
@import '~/src/assets/scss/theme.scss'

.inbox-section
  position: fixed
  display: flex
  width: 300px
  height: 738px
  padding: 0px 8px
  flex-direction: column
  align-items: flex-start
  background: #DCDCE1

.inbox-tittle
   display: flex
   align-items: center
   align-self: stretch  
   font-style: normal
   font-family: $fontPrincipal
   font-size: $tittle-2
   height: 64px
   padding: 0px 16px
   flex-shrink: 0
   font-weight: 500
   line-height: 180%
   color: #2934A5
</style>