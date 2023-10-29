<template>
    <div class="login-container">
        <div class="login-box">
            <div class="tittle">
                <h2>Login</h2>
            </div>

            <div v-if="email">
                <input type="email" class="email-box" placeholder="E-mail ou Usuário">

                <ButtonPrimary :style="buttonStyle" text="Continuar" @button-click="sendEmail" />

            </div>

            <div v-else password>
                <input type="password" class="email-box" placeholder="Senha">
                <ButtonPrimary text="Entrar" :style="buttonStyle" />
            </div>


            <div class="divisor">
                <span class="line"></span>
                <span>ou</span>
                <span class="line"></span>
            </div>

            <ButtonLogin text="Continuar com o Google " :image="google" />
            <ButtonLogin text="Continuar com o Facebook" :image="facebook" style="margin: 15px 0 ;" />
            <ButtonLogin text="Continuar com a Apple " :image="apple" />
            <button class="button-register">Cadastrar</button>


            <div class='footer'>

                <span class="line"></span>
                <div class="footer-options">
                    <a href="#" class="terms" style="text-decoration: none;">Termos e privacidade</a>

                    <SelectLang :languages="languageList" class="languages-options" />
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import ButtonPrimary from '~/components/buttons/ButtonPrimary.vue';
import ButtonLogin from '~/components/buttons/ButtonLogin.vue';
import SelectLang from '~/components/select/SelectLang.vue';

import google from '~/src/assets/icons/google.svg'
import facebook from '~/src/assets/icons/facebook.svg'
import apple from '~/src/assets/icons/apple.svg'


export default {
    name: 'Login',
    components: {
        ButtonPrimary,
        ButtonLogin,
        SelectLang
    },
    data() {

        return {
            email: true,
            password: '',
            languageList: ['Portugues (Brasil)', 'Inglês (EUA)', 'Espanhol'],
            google,
            facebook,
            apple,
        }
    },
    computed: {

        buttonStyle() {
            return {
                width: '330px',
                borderRadius: '20px',
                fontWeight: 400,
            };
        },

    },
    methods: {
        sendEmail() {
            this.email = !this.email
            console.log('click');
        }
    },

}
</script>

<style scoped lang="sass">
@import '~/src/assets/scss/theme.scss'

.login-container 
    height: 95vh
    display: flex
    justify-content: center
    align-items: center
    
.login-box
    width: 350px
    height: 500px
    padding: 10px
    display: flex
    flex-direction: column
    align-items: center
    border-radius: 15px
    box-shadow: 2px 2px 2px 2px  #d3d3d3
    
.tittle
    width: 340px
    font-family: $fontPrincipal
    font-size: $tittle-1
    display: flex
    text-align: start
    margin: 20px 0
.email-box
    width: 330px
    font-family: $fontPrincipal
    font-size:$body-2-bold
    background: #F6F6F8
    padding: 20px 0 20px 10px
    border: none
    border-radius: 10px
    margin-bottom: 15px

.divisor
    width: 330px
    display: flex
    justify-content: center
    align-items: center
    margin: 15px 0

.line
    flex-grow: 1
    border-top: 1px solid #d3d3d3
    margin: 0 10px

.button-register
    font-family: $fontPrincipal
    font-size: $body-1-regular
    display: inline-flex
    justify-content: center
    align-items: center
    cursor: pointer
    border: none
    width: 330px
    font-weight: 400
    padding: 12px 24px
    line-height: 100%
    letter-spacing: 0.48px
    background: #FFF
    color: #000   

.footer
    display: flex
    flex-direction: column
    width: 330px
    margin-bottom: 15px
    margin-top: 30px

.footer-options      
    width: 330px
    display: flex
    justify-content: space-between
    align-items: center
    margin-top: 10px

.terms 
 color: #000      

.terms:hover 
 border: 1px solid #000    

  
.languages-options:hover
 border: 1px solid #000    

    
</style>