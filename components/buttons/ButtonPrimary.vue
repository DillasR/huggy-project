<template>
    <button @click="handleClick">
        {{ text }}
    </button>
</template>

<script>
export default {
    name: 'ButtonPrimary',
    props: {
        text: {
            type: String,
            default: 'Enviar'
        }
    },
    methods: {
        handleClick() {
            this.$emit('button-click');
        },
    },
}
</script>

<style scoped lang="sass">
@import '~/src/assets/scss/theme.scss'

button
   font-family: $fontPrincipal
   font-size: $body-1-regular
   display: inline-flex
   justify-content: center
   align-items: center
   cursor: pointer
   font-weight: 600
   padding: 12px 24px
   border-radius: 8px
   line-height: 100%
   letter-spacing: 0.48px
   background: #293EA5
   color: #FFFFFF
   border: none

</style>