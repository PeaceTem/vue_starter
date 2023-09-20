<!-- <script setup>
    import { ref, computed, watch, reactive} from 'vue';

        
    // const fetchProduct = async() => {
    //     try{
    //         const response = await fetch('https://dummyjson.com/products/1')
    //         const product = ref(await response.json())
    //         console.log("The product", product.value)

    //         return product
    //     } catch (error){
    //         console.error(error)
    //     }
        
    // } 
    var product;

    // const fetchProduct = () =>{ 
    //     fetch('https://dummyjson.com/products/1')
    //     .then((res) =>{ product = res.json()})
    //     // const product = await res.json()
    //     // return product
    //     console.log("Working!")
    // }
    fetch('https://dummyjson.com/products/1')
        .then(res => res.json())
        .then(data => console.log(data))
    // const products = fetchProduct()
    // fetchProduct()
    // console.log("data", data)

    // const res = await fetch("https://jsonplaceholder.typicode.com/posts");

</script>
 -->

<!-- 
<script>
  export default {
    data() {
      return {
        products: []
      }
    },
    methods: {
      async getData() {
        const res = await fetch("https://dummyjson.com/products");
        const finalRes = await res.json();
        this.products = finalRes;
        console.log(finalRes)
      }
    },
    mounted() {
      this.getData()
    }
  }
</script> -->

<script setup>
  import { ref } from 'vue';

  const products = ref([]);

  async function getData() {
    const res = await fetch("https://dummyjson.com/products");
    const finalRes = await res.json();
    products.value = finalRes;
  }

 getData()
</script>
<!-- {{product.id}}, {{ product.title }}, {{ product.description }},
     {{ product.price }},
{{ product.discountPercentage }}, {{ product.rating }}, {{ product.stock }},
{{ product.brand }}, {{ product.category }}, {{ product.thumbnail }}, 
{{ product.images }}
 -->

<template>
    <div>
        <!-- The Products: {{ products }} -->
    </div>
    <div v-for="product in products.products" class="bg-gray-900 p-4">
        <div class="container bg-white rounded-lg p-2 mx-auto">
            <div class="rounded-sm">
                <img :src="product.thumbnail">
            </div>
            <div class="container rounded-md bg-white mx-auto mt-2">
                <span class="text-md p-2 rounded-md font-mono text-black">{{ product.title }}</span>
                <span class="bg-gray-900 text-white text-sm rounded-lg px-2 py-1 inline">{{ product.category }}</span>
            </div>

            <div class="container text-gray-700">
                <span class="mx-2">${{ product.price }}</span>
                <span class="mx-2">★{{ product.rating }}</span>
            </div>
        </div>

  </div>
</template>



