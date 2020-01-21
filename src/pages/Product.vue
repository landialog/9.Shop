<template>
  <div class="wrapper-content wrapper-content--fixed">
    <section>
      <div class="container">
      
                 <router-link :to="`/shop`">
                   <h3>Back to items</h3>
                   </router-link>
                   
        <div class="product__wrapper">

          <!-- slider -->
          <div class="product-slider">
            <carousel 
            :perPage="1" 
            :navigationEnabled="true"
            paginationActiveColor="red"
            >
              <slide v-for="(slide, index) in product.gallery" :key="index">
                <img :src="slide.img" :alt="slide.title" />
                </slide>
            </carousel>
           
          </div>

          <!-- product content -->
          <div class="product-content">
            <h1 class="title">{{ product.title }}</h1>
            <p>{{ product.descr }}</p>
          </div>
        </div>
      </div>
      <p></p>
    </section>
  </div>
</template>

<script>
export default {
  data() {
    return {
      product: null
    };
  },
  created() {
    let id = this.$route.params.id;
    this.product = this.$store.getters.getProduct(id);
    //console.log(product)
  }
};
</script>

<style lang="scss">
.product__wrapper {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
.product-slider,
.product-content {
  max-width: 48%;
  text-align: center;
}

.VueCarousel-inner { 
	visibility: visible!important;
	flex-basis: 100%!important;
	width: 100%!important;
}
</style>