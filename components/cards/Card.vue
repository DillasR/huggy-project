<template>
    <div class="card-mensage" @click="toggleColors(id)" :class="{ 'clicked': isClicked }">

        <img class="foto" :src="fotoPerfil">
        <div class="description">
            <span class="name"> {{ nameUser }}</span>
            <span class="mensage">{{ lastMensage }}</span>
        </div>
    </div>
</template>

<script>
export default {
    name: 'Card',
    props: {
        fotoPerfil: {
            type: String,
            default: ''
        },
        nameUser: {
            type: String,
            default: 'teste'
        },
        lastMensage: {
            type: String,
            default: 'teste'
        },
        id: {
            type: String,
            default: 'teste'
        },
    },

    data() {
        return {
            isClicked: false,
        };
    },
    methods: {
        toggleColors(id) {
            this.isClicked = !this.isClicked;
            console.log(id);

        },
    },

}
</script>

<style scoped lang="sass">
@import '~/src/assets/scss/theme.scss'

.card-mensage
   border-radius: 4px
   display: flex
   padding: 0px 8px
   height: 86px
   width: 275px
   gap: 12px
   flex-shrink: 0
   align-items: center
   background: #FFF
   margin-bottom: 10px


.card-mensage:hover
   background: #EEF0FC 

.foto
   width: 52px
   height: 52px
   align-items: flex-start
   flex-shrink: 0
   

.description
   display: flex
   flex-direction: column
   align-items: flex-start
   justify-content: center
   flex: 1 0 0
   align-self: stretch
.name 
  overflow: hidden
  color: #232326
  text-overflow: ellipsis
  white-space: nowrap
  font-family: $fontPrincipal
  font-size: $body-1-bold
  font-style: normal
  font-weight: 500
  line-height:  25.6px

.card-mensage:hover .name
   color: #2934A5

.clicked 
  background-color: #EEF0FC 


.clicked .name
  color: #2934A5

.mensage 
 
  overflow: hidden
  max-width: 188px
  color: #46464A
  text-overflow: ellipsis
  white-space: nowrap
  font-family: IBM Plex Sans
  font-size: 14px
  font-style: normal
  font-weight: 400
  line-height: 25.2px


</style>