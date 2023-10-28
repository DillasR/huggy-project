<template>
    <div class="custom-select">

        <div class="selected-option" @click="toggleDropdown">{{ selectedOption, '&#129171;' }} &#129171;</div>
        <ul class="dropdown" v-if="isDropdownOpen">
            <li v-for="language in languages" :key="language" @click="selectOption(language)">{{ language }}</li>
        </ul>
    </div>
</template>

<script>
export default {
    name: 'SelectLang',
    props: {
        languages: {
            type: Array,
            required: true,
        }
    },
    data() {
        return {
            isDropdownOpen: false,
            selectedOption: 'Select a language'
        };
    },
    methods: {
        toggleDropdown() {
            this.isDropdownOpen = !this.isDropdownOpen;
        },
        selectOption(option) {
            this.selectedOption = option;
            this.isDropdownOpen = false;
        }
    }
};
</script>


<style scoped lang="sass">
@import '~/src/assets/scss/theme.scss'


.custom-select 
  position: relative
  

.selected-option 
  background-color: #fff
  border: none
  padding: 5px
  cursor: pointer

.dropdown 
  display: none
  position: absolute
  background-color: #fff
  border: none
  border-top: none
  list-style: none
  padding: 0
  margin: 0

.dropdown li 
  padding: 5px
  cursor: pointer
  margin-bottom: 5px


.custom-select  .dropdown 
  display: block
</style>
