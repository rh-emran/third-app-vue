<template>
  <h2 class="text-center font-bold text-lg underline">Products List</h2>
  <div class="flex flex-wrap -mx-4 mb-4">
    <div
      v-for="(product, index) in products"
      :key="index"
      class="w-1/3 px-4 mt-6"
    >
      <div class="border border-gray-300 p-4 h-full bg-green-100 rounded-md">
        <h2 class="text-center mb-2">({{ product.id }})</h2>
        <h2
          class="text-center font-bold mb-4 text-lg p-2 bg-green-200 rounded-md"
        >
          {{ product.title }}
        </h2>
        <p class="mb-3">Description: {{ product.description }}</p>
        <img
          v-bind:src="product.thumbnail"
          v-bind:alt="product.title"
          class="w-full h-60 rounded-md block"
        />
        <p class="mt-6 text-center">
          <a
            href="#"
            class="px-4 py-2 bg-white rounded-md text-gray-500 hover:text-red-500 hover:bg-red-50 border border-blue-400"
            >View Details</a
          >
        </p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Home",
  data() {
    return {
      products: [],
    };
  },
  mounted() {
    fetch("https://dummyjson.com/products")
      .then((response) => response.json())
      .then((json_data) => (this.products = json_data.products));
    // console.log(this.products);
  },
};
</script>
