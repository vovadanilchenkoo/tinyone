<template lang="pug">
  section.features
    .container
      h1.features__title {{data.features_title}}
      h2.features__subtitle {{data.subtitle}}
      .features-list
        .feature-item
          .feature-item-left
            img(src='../../assets/img/icon-font-1.png' alt='feature icon')
          .feature-item-right
            span Fully responsive
            p Lorem ipsum dolor sit amet, consectetur adipiscing elit. Praesent vitae eros eget tellus tristique bibendum.
        .feature-item
          .feature-item-left
            img(src='../../assets/img/icon-font-2.png' alt='feature icon')
          .feature-item-right
            span Fully responsive
            p Lorem ipsum dolor sit amet, consectetur adipiscing elit. Praesent vitae eros eget tellus tristique bibendum.
        .feature-item
          .feature-item-left
            img(src='../../assets/img/icon-font-3.png' alt='feature icon')
          .feature-item-right
            span Fully responsive
            p Lorem ipsum dolor sit amet, consectetur adipiscing elit. Praesent vitae eros eget tellus tristique bibendum.
        .feature-item
          .feature-item-left
            img(src='../../assets/img/icon-font-4.png' alt='feature icon')
          .feature-item-right
            span Fully responsive
            p Lorem ipsum dolor sit amet, consectetur adipiscing elit. Praesent vitae eros eget tellus tristique bibendum.
        .feature-item
          .feature-item-left
            img(src='../../assets/img/icon-font-5.png' alt='feature icon')
          .feature-item-right
            span Fully responsive
            p Lorem ipsum dolor sit amet, consectetur adipiscing elit. Praesent vitae eros eget tellus tristique bibendum.
        .feature-item
          .feature-item-left
            img(src='../../assets/img/icon-font-6.png' alt='feature icon')
          .feature-item-right
            span Fully responsive
            p Lorem ipsum dolor sit amet, consectetur adipiscing elit. Praesent vitae eros eget tellus tristique bibendum.
</template>

<script>
import data from '../../data/data.json';

export default {
  data() {
    return {
      data: data
    }
  }
}
</script>

<style lang="sass">
@import 'TinyoneFeatures'
</style>