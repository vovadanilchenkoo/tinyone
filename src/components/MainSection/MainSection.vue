<template lang="pug">
  section.main-sect
    .container
      header.header(:class='{active: isActive}')
        div.logo
          img(src='@/assets/img/fingerprint.png' alt='logo')
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
        .slide(v-for='slide in slider')
          .slide-left
            h1.slide-left__title {{slide.title}}
            h2.slide-left__subtitle {{slide.subtitle}}
            p.slide-left__txt {{slide.txt}}
            .soc-icons 
              img(:src='require(`@/assets/img/${slide.icons[0]}`)' alt='social icon')
              img(:src='require(`@/assets/img/${slide.icons[1]}`)' alt='social icon')
              img(:src='require(`@/assets/img/${slide.icons[2]}`)' alt='social icon')
          .slide-right
            img(class='slide-right__img' :src='require(`@/assets/img/${slide.img}`)' alt='tablet image')
</template>

<script>
import carousel from 'vue-owl-carousel';
import data from '@/data/data.json';

export default {
  data() {
    return {
      menu_items: data.main_section.menu_items,
      slider: data.main_section.slider,
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
