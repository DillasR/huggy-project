<template>
  <div>
    <div v-if="loginBoxVisible" class="login-content">
      <div class="login">
        <h3>Área de login</h3>
        <p>Faça login para acessar nosso super-aplicativo</p>
        <div @click="showLoginBox">
          <ButtonPrimary text="Fazer login com a Huggy" style="margin-top: 64px; margin-bottom: 48px;" />
        </div>
      </div>
    </div>

    <div v-else>
      <Login />
    </div>
  </div>
</template>

<script>
import ButtonPrimary from '~/components/buttons/ButtonPrimary.vue';
import Login from '~/components/logins/Login.vue';


export default {
  name: 'AreaLogin',
  components: {
    ButtonPrimary,
    Login
  },
  data() {
    return {
      loginBoxVisible: true,
    }
  },
  methods: {

    showLoginBox() {
      console.log("===aqui")
      this.loginBoxVisible = false;
    },


  }
}
</script>


<style scoped lang="sass">
@import '~/src/assets/scss/theme.scss'

.login-content 
  height: 95vh
  display: flex
  justify-content: center
  align-items: center

  .login 
    display: flex
    flex-direction: column
    justify-content: center
    align-items: center
  
  h3
    color: #2934A5
    font-family: $fontPrincipal
    font-size: $tittle-1
    font-style: normal
    font-weight: 400
    line-height: 46.8px 

  p
     font-family: $fontPrincipal
     font-size: $body-1-regular
     font-style: normal
     font-weight: 400
     line-height: 28.8px 

  
</style>
