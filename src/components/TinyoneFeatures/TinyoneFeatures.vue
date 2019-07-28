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

.features__title,
.features__subtitle
  text-align: center

.features__title
  margin: 118px 0 17px

.features__subtitle
  margin: 0 auto 88px
  max-width: 732px

.features-list
  display: flex
  flex-wrap: wrap
  justify-content: center

.feature-item
  display: flex
  width: 100%
  max-width: 277px
  margin-right: 34px
  margin-bottom: 88px
  &:nth-of-type(3n)
      margin-right: 0
  img 
    margin-right: 34px
  span
    display: block
    margin-bottom: 15px
  p 
    color: #898989

.feature-item-left
  width: 25%

</style>