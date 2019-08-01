<template lang="pug">
  section.features
    .container
      h1.features__title {{data.features_title}}
      h2.features__subtitle {{data.subtitle}}
      .features-list
        .feature-item(v-for='feature in data.features')
          .feature-item-left
            img(:src='require(`@/assets/img/${feature.url}`)' alt='feature icon')
          .feature-item-right
            span {{feature.title}}
            p {{feature.txt}}
</template>

<script>
import data from '@/data/data.json';

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