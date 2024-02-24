
  <template>
    <div class="container mt-5">
      <h1>Our Products</h1>
      <div class="row ">
        <div class="col-md-4 mb-4" v-for="product in products" :key="product.id">
          <div class="card w-100">
            <img src="@/assets/dummy1.jpg" class="card-img-top" alt="Product Image">
            <div class="card-body">
              <h5 class="card-title">{{ product.name }}</h5>
              <p class="card-text">Price: {{ product.price }}</p>
              <a href="#" @click="viewDetails(product.id)" class="btn btn-primary">View</a>
            </div>
          </div>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  import products from './services/products.ts'
  export default {
    data() {
      return {
       products
      };
    },
    methods: {
      viewDetails(productId) {
      
        this.$router.push(`/products/${productId}`);
      },
    },
  };
  </script>
  <style scoped>
  
  .card {
    border: 1px solid #ddd;
    border-radius: 8px;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  }
  
  .card-title {
    font-size: 1.25rem;
  }
  
  .card-text {
    font-size: 1rem;
  }
  
  .btn-primary {
    background-color: #007bff;
    border-color: #007bff;
  }
  </style>
  