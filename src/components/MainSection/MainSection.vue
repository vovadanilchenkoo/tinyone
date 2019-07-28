<template lang="pug">
  section.main-sect
    .container
      header.header(:class='{active: isActive}')
        div.logo
          img(src='../../assets/img/fingerprint.png' alt='logo')
          span tinyone
        button(type='button' class='header-mnu-btn' @click='mnuBtn')
          span.header-mnu-btn__icon
            span
          span.header-mnu-btn__txt Menu
        nav.nav
          ul.nav-list
            li.nav-list__item(v-for='item in menu_items')
              a(:href='item.link' class='nav-list__link') {{item.title}}

      carousel(:items='1' :nav='false' class='carousel-wrap')
        .slide
          .slide-left
            h1.slide-left__title Inspire your inspiration
            h2.slide-left__subtitle Simple to use for your app, products showcase and your inspiration
            p.slide-left__txt Lorem ipsum dolor sit amet, consectetur adipiscing elit. Praesent vitae eros eget tellus tristique bibendum. Donec rutrum sed sem quis venenatis. Proin viverra risus a eros volutpat tempor. In quis arcu et eros porta lobortis sit
            .soc-icons 
              img(src='../../assets/img/icon-fa-apple.png' alt='social icon')
              img(src='../../assets/img/icon-fa-android.png' alt='social icon')
              img(src='../../assets/img/icon-fa-windows.png' alt='social icon')
          .slide-right
            img(class='slide-right__img' src='../../assets/img/tablet.jpg' alt='tablet image')
        .slide
          .slide-left
            h1.slide-left__title Inspire your inspiration
            h2.slide-left__subtitle Simple to use for your app, products showcase and your inspiration
            p.slide-left__txt Lorem ipsum dolor sit amet, consectetur adipiscing elit. Praesent vitae eros eget tellus tristique bibendum. Donec rutrum sed sem quis venenatis. Proin viverra risus a eros volutpat tempor. In quis arcu et eros porta lobortis sit
            .soc-icons 
              img(src='../../assets/img/icon-fa-apple.png' alt='social icon')
              img(src='../../assets/img/icon-fa-android.png' alt='social icon')
              img(src='../../assets/img/icon-fa-windows.png' alt='social icon')
          .slide-right
            img(class='slide-right__img' src='../../assets/img/tablet.jpg' alt='tablet image')
        .slide
          .slide-left
            h1.slide-left__title Inspire your inspiration
            h2.slide-left__subtitle Simple to use for your app, products showcase and your inspiration
            p.slide-left__txt Lorem ipsum dolor sit amet, consectetur adipiscing elit. Praesent vitae eros eget tellus tristique bibendum. Donec rutrum sed sem quis venenatis. Proin viverra risus a eros volutpat tempor. In quis arcu et eros porta lobortis sit
            .soc-icons 
              img(src='../../assets/img/icon-fa-apple.png' alt='social icon')
              img(src='../../assets/img/icon-fa-android.png' alt='social icon')
              img(src='../../assets/img/icon-fa-windows.png' alt='social icon')
          .slide-right
            img(class='slide-right__img' src='../../assets/img/tablet.jpg' alt='tablet image')

</template>

<script>
import carousel from 'vue-owl-carousel';
import data from '../../data/data.json';

export default {
  data() {
    return {
      menu_items: data.main_section.menu_items,
      isActive: false
    };
  },
  methods: {
    mnuBtn: function() {
      this.isActive = !this.isActive
    }
  },
  components: { carousel }
}
</script>

<style lang="sass">
.main-sect
  background-color: #fcdb00

.header
  display: flex
  align-items: center
  justify-content: space-between
  padding: 61px 0

.header.active
  .header-mnu-btn__icon 
    &:before
      transition: transform .2s linear
      transform: rotate(45deg) translate(5px, 9px)
    &:after
      transition: transform .2s linear
      transform: rotate(132deg) translate(-5px, 9px)
    span
      opacity: 0
      transition: opacity .2s linear
  .nav 
    height: 144px
    transition: height .2s linear

.logo
  display: flex
  align-items: center

.logo 
  span
    font-weight: 700
    font-size: 30px
    margin-left: 10px

.header-mnu-btn
  display: none
  padding: 0
  outline: none
  &:focus
    outline: none

.header-mnu-btn__icon
  position: relative
  display: inline-flex
  align-items: center
  justify-content: center
  width: 30px
  height: 24px
  margin-right: 15px
  &:before,
  &:after
    content: ''
    position: absolute
    width: 100%
    border-radius: 4px
    height: 4px
    background: #010101
    transition: transform .2s linear
  &:before
    left: 0
    top: 0
    // transform: rotate(45deg)
  &:after
    right: 0
    bottom: 0
    // transform: rotate(-45deg)
  span 
    border-radius: 4px
    width: 100%
    height: 4px
    background: #010101
    opacity: 1
    transition: opacity .2s linear

.header-mnu-btn__txt
  color: #010101
  font-family: inherit
  font-weight: 700
  font-size: 22px

.nav
  width: 100%
  max-width: 350px

.nav-list
  display: flex
  align-items: center
  justify-content: space-between
  transition: height .2s linear

.nav-list__link
  font-size: 22px
  font-weight: 700
  color: inherit
  &:hover,
  &:focus
    color: #fff

// slider
.owl-carousel 
  .owl-item 
    img
      width: auto

.slide 
  display: flex
  align-items: center
  justify-content: space-between

.slide-left__subtitle
  margin: 22px 0
  max-width: 309px

.slide-left__txt
  margin-bottom: 40px
  max-width: 390px
  color: #555555

.owl-carousel 
  .owl-item 
    .soc-icons 
      img
        display: inline-block

.soc-icons 
  img 
    display: inline-block
    &:nth-child(2)
      margin: 0 38px

.slide-right
  padding-left: 20px

.slide-right__img
  width: 100%
  max-width: 316px
  border-radius: 20px

.owl-theme 
  .owl-nav.disabled + .owl-dots
    margin: 0
    padding: 44px 0 49px
  .owl-dot
    outline: none
    &:focus
      outline: none
</style>
