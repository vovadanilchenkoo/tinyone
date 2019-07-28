<template lang="pug">
  footer.footer
    .container
      h1.footer__title {{data.footer_title}}
      h2.footer__subtitle {{data.subtitle}}
      
      form(@submit='checkForm' :class="['input-group subscription-form', isEmailValid()]" method="POST" ref='subscriptionForm' action="https://formspree.io/")
        input(type="email" name="email" v-model='email' placeholder="Enter your email to update")
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
    isEmailValid: function() {
      if( this.email == "" ) {
        return "";
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
    checkForm: function(e) {
      this.$refs.subscriptionForm.setAttribute('action', `https://formspree.io/${this.email}`);
      if(this.sendForm) {
        return true;
      } else {
        e.preventDefault();
      };
    }
  }
}
</script>

<style lang="sass">

.footer
  background: #000

.footer__title,
.footer__subtitle
  text-align: center 

.footer__title
  color: #fcdb00
  padding: 96px 0 17px

.footer__subtitle
  max-width: 732px
  margin: 0 auto 41px
  color: #898989

.subscription-form
  display: flex
  align-items: center
  justify-content: space-between
  max-width: 727px
  margin: 0 auto
  input 
    max-width: 580px
    width: 100%
    border: none
    height: 46px 
    border-radius: 6px
    color: #898989
    font-size: 16px
    padding: 0 24px
    margin-right: 21px
    outline: none
    border: 2px solid transparent
    transition: border .2s linear
    &:focus
      outline: none
  button 
    max-width: 126px
    width: 100%
    border: none
    border-radius: 6px
    background: #fcdb00
    height: 50px
    font-size: 16px
    font-weight: 700
    text-transform: uppercase
    color: #010101
    text-align: center 
    cursor: pointer

.has-error
  input
    border: 2px solid #d50000
    transition: border .2s linear
.has-success
  input
    border: 2px solid #00c853
    transition: border .2s linear

.footer-soc-icons
  margin: 79px auto 134px
  display: flex
  align-items: center
  justify-content: space-between
  max-width: 240px

.footer-bottom
  display: flex
  justify-content: space-between
  padding-bottom: 96px

.footer-bottom-list 
  .footer-contacts
    li 
      text-transform: uppercase
  li,a
    font-size: 16px
    color: #fff
  a
    &:hover,
    &:focus
      color: #fcdb00
</style>