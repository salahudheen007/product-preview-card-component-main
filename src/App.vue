<script>
  import productVue from './components/product.vue';
export default {
  name:'App',
  components:{
    productVue}
  
}
</script>

<template>
  <div class="container">
    <product-vue/>
    <div class="attribution text-center my-5">
      Challenge by <a href="https://www.frontendmentor.io/challenges/product-preview-card-component-GO7UmttRfa" target="_blank">Frontend Mentor</a>. 
      Coded by <a href="https://www.linkedin.com/in/salahudheen-k-7574ba1a6/">Salahudheen</a>.
    </div>
  </div>
</template>

<style scoped>
  .container{
    width: fit-content;
  }
</style>
