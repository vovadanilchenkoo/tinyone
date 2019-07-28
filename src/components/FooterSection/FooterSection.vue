<template lang="pug">
  footer.footer
    .container
      h1.footer__title {{data.footer_title}}
      h2.footer__subtitle {{data.subtitle}}
      
      form(
        method='POST'
        @submit='checkForm' 
        ref='subscriptionForm' 
        :class="['input-group subscription-form', isEmailValid()]" 
      )
        input(required type="email" name="email" v-model='email' placeholder="Enter your email to update")
        textarea(hidden name='message') Привіт, це перевірка тестового завдання, яке зробив Володимир
        button(type="submit") Submit
      
      .footer-soc-icons
        a(href='##')
          img(src='../../assets/img/facebook_ico.png' alt='facebook icon')
        a(href='##')
          img(src='../../assets/img/twitter_ico.png' alt='twitter icon')
        a(href='##')
          img(src='../../assets/img/google_+_ico.png' alt='google+ icon')
        a(href='##')
          img(src='../../assets/img/pinterest_ico.png' alt='pinterest icon')

      .footer-bottom
        .footer-contacts
          ul.footer-bottom-list
            li HALOVIETNAM LTD
            li 66, Dang Van ngu, Dong Da
            li Hanoi, Vietnam
            li contact@halovietnam.com
            li +844 35149182
        .footer-bottom-item
          ul.footer-bottom-list 
            li 
              a(href='##') Examples
            li 
              a(href='##') Shop
            li 
              a(href='##') License 
        .footer-bottom-item
          ul.footer-bottom-list 
            li 
              a(href='##') Contact
            li 
              a(href='##') About
            li 
              a(href='##') Privacy 
            li 
              a(href='##') Terms 
        .footer-bottom-item
          ul.footer-bottom-list 
            li 
              a(href='##') Download
            li 
              a(href='##') Support
            li 
              a(href='##') Documents 
        .footer-bottom-item
          ul.footer-bottom-list 
            li 
              a(href='##') Media
            li 
              a(href='##') Blog
            li 
              a(href='##') Forums 
</template>

<script>
import data from '../../data/data.json';

export default {
  data() {
    return {
      data: data,
      sendForm: false,
      email: '',
      reg: /^(([^<>()\[\]\\.,;:\s@"]+(\.[^<>()\[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,24}))$/
    }
  },
  methods: {
    isEmailValid() {
      if( this.email == '' ) {
        return '';
      } else {
        if( this.reg.test(this.email) ) {
          this.sendForm = true;
          return 'has-success';
        } else {
          this.sendForm = false;
          return 'has-error';
        };
      }
    },
    checkForm(e) {
      if(this.sendForm) {
        this.$refs.subscriptionForm.setAttribute('action', `https://formspree.io/${this.email}`);
        return true;
      } else {
        e.preventDefault();
      };
    }
  }
}
</script>

<style lang="sass">
@import 'FooterSection'
</style>