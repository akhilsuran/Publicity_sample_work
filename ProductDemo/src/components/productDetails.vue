
  <template>
    <div class="container mt-5">
      <div class="card">
        <img src="@/assets/dummy2.jpg" class="card-img-top" style="max-height: 250px;" alt="Product Image">
        <div class="card-body">
          <h5 class="card-title">{{ product.name }}</h5>
          <p class="card-text">Price: {{ product.price }}</p>
          <p class="card-text"> {{ product.description }}</p>
          <a href="#" class="btn btn-primary">Buy Now</a> <br> <br>
          
<router-link to="/"><a  class="btn btn-secondary"><svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-backspace" viewBox="0 0 16 16">
  <path d="M5.83 5.146a.5.5 0 0 0 0 .708L7.975 8l-2.147 2.146a.5.5 0 0 0 .707.708l2.147-2.147 2.146 2.147a.5.5 0 0 0 .707-.708L9.39 8l2.146-2.146a.5.5 0 0 0-.707-.708L8.683 7.293 6.536 5.146a.5.5 0 0 0-.707 0z"/>
  <path d="M13.683 1a2 2 0 0 1 2 2v10a2 2 0 0 1-2 2h-7.08a2 2 0 0 1-1.519-.698L.241 8.65a1 1 0 0 1 0-1.302L5.084 1.7A2 2 0 0 1 6.603 1zm-7.08 1a1 1 0 0 0-.76.35L1 8l4.844 5.65a1 1 0 0 0 .759.35h7.08a1 1 0 0 0 1-1V3a1 1 0 0 0-1-1z"/>
</svg>  Product List</a></router-link>
        </div>
      </div>
    </div>
  </template>
  <script>
   import products from './services/products.ts'
  export default {
    data() {
      return {
        product: {},
      };
    },
 
    created() {
    
      const productId = this.$route.params.id;
      let productName;
      let productDescription;
      let price;
    
    if(products){
        products.forEach(element => {
            if(element.id== productId){
                productName=element.name;
                productDescription=element.description;
                price=element.price
            }
        });
    }
      this.product = {
        id: productId,
        name:productName,
        description: productDescription,
        price: price,
      };
    },
  };
  </script>
  <style scoped>
 
  .card {
    border: 1px solid #ddd;
    border-radius: 8px;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
    width: 100%; /* Ensure the card spans the full width */
  }
  
  .card-title {
    font-size: 1.25rem;
  }
  
  .card-text {
    font-size: 1rem;
  }
  </style>