<template>
  <div class='container-fluid moore-gradient moore-navy'>

    <div class='p-3'>

      <h2> Edit Product </h2>

    </div>

    <product-form :productToEdit='getProduct' :formType='formType'> </product-form>

  </div>
</template>

<script>
import { mapGetters } from 'vuex'


import ProductForm from './ProductForm.vue'

export default {
  name: 'EditProduct',

  components: {
    ProductForm
  },

  props: [],

  data() {
    return {
      productId: parseInt(this.$route.params.id),
      formType: 'edit',
    }
  },   
  computed: {
      ...mapGetters('product', ['getProductById']),

      getProduct() {
            let gotProduct = this.getProductById(this.productId)
            return gotProduct
          }
    },
}

</script>

<style>

</style>
