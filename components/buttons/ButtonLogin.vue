<template>
    <button id="button-design">
        <img :src="image" alt="">
        {{ text }}
    </button>
</template>

<script>
export default {
    name: 'ButtonLogin',
    props: {
        text: {
            type: String,
            default: 'Enviar'
        },
        image: {
            type: String,
            default: ''
        },
    },
}
</script>

<style scoped lang="sass">

@import '~/src/assets/scss/theme.scss'

#button-design
 font-family: $fontPrincipal
 font-size: $body-1-regular
 display: flex
 align-items: center
 justify-content: center
 cursor: pointer
 width: 330px
 font-weight: 400
 padding: 12px 24px
 border-radius: 20px
 line-height: 100%
 letter-spacing: 0.48px
 background: #fff
 color:#000
 border: 1px solid #d3d3d3


img
    margin-right: 10px    

#button-design:hover
    background: #d3d3d3


</style>


        