<template lang='pug'>
  main#app
    MainSection
    TinyoneFeatures
    FooterSection
</template>

<script>
import MainSection from './components/MainSection/MainSection'
import TinyoneFeatures from './components/TinyoneFeatures/TinyoneFeatures'
import FooterSection from './components/FooterSection/FooterSection'

export default {
  name: 'App',
  components: {
    MainSection,
    TinyoneFeatures,
    FooterSection
  }
}
</script>

<style lang='sass'>
/* Default styles */
*,
*::before,
*::after
  box-sizing: border-box

html 
  box-sizing: border-box
  -ms-overflow-style: scrollbar
  overflow-x: hidden

body
  overflow-x: hidden
  margin: 0
  font-family: 'PT Sans', sans-serif
  font-weight: 400
  color: #010101

ul 
  padding: 0
  margin: 0
li
  list-style-type: none

a 
  text-decoration: none

a:hover
  text-decoration: none

a,button
  transition: all .2s linear

a:hover, 
button:hover
  transition: all .2s linear

h1,h2,h3,h4,h5,h6,p 
  margin: 0

h1
  font-size: 32px
  font-weight: 700

h2 
  font-size: 20px
  color: #313841
  font-weight: 400

.container 
  width: 100%
  padding-right: 15px
  padding-left: 15px
  margin-right: auto
  margin-left: auto

@media (min-width: 768px)
  .container
    max-width: 700px

@media (min-width: 992px)
  .container
    max-width: 929px
</style>