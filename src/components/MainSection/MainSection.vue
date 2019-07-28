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
    mnuBtn() {
      this.isActive = !this.isActive
    }
  },
  components: { carousel }
}
</script>

<style lang="sass">
@import 'MainSection'
</style>
