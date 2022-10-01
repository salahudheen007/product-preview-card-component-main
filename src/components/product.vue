<template>
  <div class="card m-2" style="max-width: 540px">
    <div class="row g-0">
      <div class="col-md-6">
        <img :src="ProductImage" class="img-fluid" alt="..." />
      </div>
      <div class="col-md-6">
        <div class="card-body p-4 pe-md-5">
          <p class="perfume mb-1 pt-md-3 pb-md-1">PERFUME</p>
          <h1 class="card-title pt-md-2 pb-md-3">
            Gabrielle Essence Eau De Perfume
          </h1>
          <p class="card-text">
            A floral, solar and voluptuous interpretation composed by Olivier
            Polge, Perfumer-Creator for the House of CHANEL.
          </p>
          <div class="row py-md-3">
            <div class="col"><h1 class="price-new">$149.99</h1></div>
            <div class="col">
              <p class="price-old pt-md-3 pt-2"><del class="">$169.99</del></p>
            </div>
          </div>
          <button class="btn py-2 my-2 py-md-3" type="button">
            <img :src="ShopingCartIcon" alt="CART ICON" class="cart-icon">
             Add to Cart
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import ProductImageMobile from "../assets/images/image-product-mobile.jpg";
import ProductImageDesktop from "../assets/images/image-product-desktop.jpg";
import ShopingCartIcon from "../assets/images/icon-cart.svg";
export default {
  name: "Product",
  data() {
    return {
      ProductImageMobile: ProductImageMobile,
      ProductImageDesktop: ProductImageDesktop,
      ProductImage:'',
      ShopingCartIcon:ShopingCartIcon
    };
  },
  methods: {
    updateImage() {
      if (window.innerWidth > 768) {
        this.ProductImage = ProductImageDesktop;
      } else {
        this.ProductImage = ProductImageMobile;
      }
    },
  },
  mounted() {
    this.updateImage();
  },
  created() {
    window.addEventListener("resize", this.updateImage);
  },
  destroyed() {
    window.removeEventListener("resize", this.updateImage);
  },
};
</script>

<style scoped>
.card {
  overflow: hidden;
}
.perfume {
  color: var(--Dark-grayish-blue);
  letter-spacing: 4px;
  font-family: "Montserrat", sans-serif;
  font-weight: 500;
}
.card-title {
  font-family: "Fraunces", serif;
  font-weight: 700;
  color: var(--Very-dark-blue);
}
.card-text {
  color: var(--Dark-grayish-blue);
  font-family: "Montserrat", sans-serif;
}
.price-new {
  font-family: "Fraunces", serif;
  font-weight: 700;
  color: var(--Dark-cyan);
}.price-old{
    color: var(--Dark-grayish-blue);
  font-family: "Montserrat", sans-serif;
}
.btn {
  width: 100%;
  background-color: var(--Dark-cyan);
  color: white;
  font-family: "Montserrat", sans-serif;
}
.btn:hover{
    background-color: hsl(155, 45%, 21%);
    color: white;
}
.cart-icon{
    margin-right:8px ;
}
@media only screen and (min-width: 769px) {
  .card {
    min-width: 45rem;
  }
}
</style>