<template>
  <div class="bg-gray-100">
    <!-- Navbar -->
    <nav class="bg-gray-800 p-4 text-black">
      <div class="container mx-auto flex justify-between items-center">
        <h1 class="text-2xl font-bold">Vinyl Shop</h1>
        <div>
          <a href="#" class="mr-4">Home</a>
          <a href="#" class="mr-4">Catalog</a>
          <a href="#" class="mr-4">Contact</a>
        </div>
      </div>
    </nav>

    <!-- Hero Image -->
    <div class="relative bg-gray-700 h-64">
      <img src="https://images.unsplash.com/photo-1582730147924-d92f4da00252?q=80&w=1000&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxzZWFyY2h8Nnx8dmlueWx8ZW58MHx8MHx8fDA%3D" alt="Vinyl Hero" class="object-cover w-full h-full" />
      <div class="absolute inset-0 bg-black opacity-40"></div>
      <div class="absolute inset-0 flex items-center justify-center">
        <h2 class="text-4xl font-bold text-white">Discover Your Vinyl Favorites</h2>
      </div>
    </div>

    <!-- Vinyl Cards -->
    <div class="container mx-auto p-8 grid grid-cols-1 md:grid-cols-3 lg:grid-cols-3 gap-8 mt-8">
      <div v-for="vinyl in vinyls" :key="vinyl.id" class="bg-white p-4 shadow-md rounded-md">
        <img :src="vinyl.image" :alt="vinyl.title" class="mb-4 rounded-md aspect-square">
        <h2 class="text-lg font-semibold">{{ vinyl.title }}</h2>
        <p class="text-gray-600">{{ vinyl.artist }}</p>
        <p class="mt-2 text-green-500 font-bold">€{{ vinyl.price.toFixed(2) }}</p>
        <button @click="addToCart(vinyl)" class="mt-4 bg-green-500 text-black px-4 py-2 rounded-md hover:bg-green-600 focus:outline-none focus:ring focus:border-green-300">
          Add to Cart
        </button>
      </div>
    </div>


    <footer class="bg-gray-800 text-black p-4 mt-8">
      <div class="container mx-auto text-center">
        <p>&copy; 2023 Vinyl Shop. All rights reserved.</p>
      </div>
    </footer>
  </div>
</template>

<script>
export default {
  data() {
    return {
      vinyls: [
        {
          id: 1,
          title: 'Eminem - The Slim Shady LP',
          artist: 'Eminem',
          price: 19.99,
          image: 'https://images-eu.ssl-images-amazon.com/images/I/71n0xmxpw7L._AC_UL600_SR600,600_.jpg', 
        },
        {
          id: 2,
          title: '2Pac - All Eyez on Me',
          artist: '2Pac',
          price: 54.99,
          image: 'https://m.media-amazon.com/images/I/81y8N1Dq+DL._UF1000,1000_QL80_.jpg', 
        },
        {
          id: 3,
          title: 'Eminem - Marshal never more',
          artist: 'Eminem',
          price: 39.99,
          image: 'https://m.media-amazon.com/images/I/816SvCUNM+L._UF894,1000_QL80_.jpg', 
        },
        {
          id: 4,
          title: '2Pac - Life',
          artist: '2Pac',
          price: 94.99,
          image: 'https://media.s-bol.com/jO7Gxjp2Wyrv/v5OqxV/1200x1200.jpg', 
        },
      ],
      cart: [],
    };
  },
  methods: {
    addToCart(vinyl) {
      this.cart.push(vinyl);
    },
  },
};
</script>

<style scoped>
body {
  color: #333;
}

</style>
