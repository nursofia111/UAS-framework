<template>
  <div class="container mx-auto px-80 my-8">
    <div class="relative overflow-x-auto">
      <form @submit.prevent="TambahData">
        <div class="mb-6">
          <label for="mata_kuliah" class="block mb-2 text-sm font-medium text-gray-900 dark:text-white">matakuliah</label>
          <input
            type="text"
            id="mata_kuliah"
            class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500"
            placeholder="masukan matakuliah"
            required
          />
        </div>
        <div class="mb-6">
          <label for="sks" class="block mb-2 text-sm font-medium text-gray-900 dark:text-white">sks</label>
          <input
            type="number"
            id="sks"
            class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500"
            required
          />
        </div>
        <button
          type="submit"
          class="text-white bg-blue-700 hover:bg-blue-800 focus:ring-4 focus:outline-none focus:ring-blue-300 font-medium rounded-lg text-sm w-full sm:w-auto px-5 py-2.5 text-center dark:bg-blue-600 dark:hover:bg-blue-700 dark:focus:ring-blue-800"
        >
          Submit
        </button>
        <br />
        <button
          type="submit"
          class="text-white bg-blue-700 hover:bg-blue-800 focus:ring-4 focus:outline-none focus:ring-blue-300 font-medium rounded-lg text-sm w-full sm:w-auto px-5 py-2.5 text-center dark:bg-blue-600 dark:hover:bg-blue-700 dark:focus:ring-blue-800"
        >
          <nuxt-link to="/">kembali</nuxt-link>
        </button>
      </form>
    </div>
  </div>
</template>

<script>
import axios from 'axios';

export default {
  data() {
    return {
      mata_kuliah: '',
      sks: '',
    };
  },
  methods: {
    async addData() {
      try {
        const response = await axios.post('https://64abc8e39edb4181202e87b6.mockapi.io/akademik/v1/matakuliah', {
          mata_kuliah: this.mata_kuliah,
          sks: this.sks,
        });
        console.log(response.data); // Output the response from the API if needed
        // Reset form
        this.mata_kuliah = '';
        this.sks = '';
      } catch (error) {
        console.error(error);
      }
    },
  },
};
</script>

<style></style>
