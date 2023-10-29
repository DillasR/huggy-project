<template>
    <div class="inbox-section">
        <h1 class="inbox-tittle">Minhas mensagens</h1>
        <div v-for="item in cardInfo">
            <Card :fotoPerfil="item.fotoPerfil" :nameUser="item.nameUser" :lastMensage="item.lastMensage" :id="item.id" />
        </div>
    </div>
</template>

<script>
import Card from '~/components/cards/Card.vue';

import agostinho from '~/src/assets/fotoPerfil/agostinho.png';
import beicola from '~/src/assets/fotoPerfil/beicola.png';
import lineu from '~/src/assets/fotoPerfil/lineu.png'



export default {
    name: 'chat',
    components: {
        Card,
    },
    data() {
        return {
            agostinho,
            beicola,
            lineu,
            cardInfo: [
                {
                    id: 1, isActive: false,
                    fotoPerfil: agostinho,
                    nameUser: 'Agostinho',
                    lastMensage: '199,00',
                },
                {
                    id: 2, isActive: false,
                    fotoPerfil: beicola,
                    nameUser: 'Beiçola',
                    lastMensage: 'precisamos ver dos fiado, tem mais de 20 pasteu',
                },
                {
                    id: 3, isActive: false,
                    fotoPerfil: lineu,
                    nameUser: 'Lineu',
                    lastMensage: 'Sobre a inspeção do outro dia',
                },
            ],
        };

    },

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