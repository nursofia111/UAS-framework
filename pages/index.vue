<template>
  <!-- <div class="container mx-auto mt-8">
    <div class="relative overflow-x-auto">
      <button
        type="button"
        class="text-white bg-green-500 hover:bg-green-600 focus:outline-none focus:ring-4 focus:ring-green-100 font-medium rounded-full text-sm px-5 py-2.5 text-center mr-2 mb-2 dark:bg-green-600 dark:hover:bg-green-700 dark:focus:ring-green-800"
      >
        <NuxtLink to="/matakuliah/CreateData">Tambah Data</NuxtLink>
      </button>
      <table class="w-full text-sm text-left text-gray-500 dark:text-gray-400">
        <thead class="text-xs text-gray-700 uppercase bg-sky-500 dark:bg-gray-700 dark:text-gray-400">
          <tr>
            <th scope="col" class="text-base px-6 py-3">Id</th>
            <th scope="col" class="text-base px-6 py-3">Mata Kuliah</th>
            <th scope="col" class="text-base px-6 py-3">Total SKS</th>
            <th scope="col" class="text-base px-6 py-3">Detail</th>
          </tr>
        </thead>
        <tbody>
          <tr class="bg-white dark:bg-gray-800" v-for="mk in Matakuliah" :key="mk.id">
            <th scope="row" class="px-6 py-4 font-medium text-gray-900 whitespace-nowrap dark:text-white">
              {{ mk.id }}
            </th>
            <td class="text-base px-6 py-4">{{ mk.matakuliah }}</td>
            <td class="text-base px-6 py-4">{{ mk.sks }}</td>
            <td class="text-base px-6 py-4">
              <button
                type="button"
                class="text-white bg-red-700 hover:bg-red-800 focus:outline-none focus:ring-4 focus:ring-red-300 font-medium rounded-full text-sm px-5 py-2.5 text-center mr-2 mb-2 dark:bg-red-600 dark:hover:bg-red-700 dark:focus:ring-red-900"
              >
                <svg class="w-6 h-6 text-gray-800 dark:text-white" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 12 20">
                  <path
                    stroke="currentColor"
                    stroke-linecap="round"
                    stroke-linejoin="round"
                    stroke-width="2"
                    d="M10.335 6.514 6.91 1.464a1.122 1.122 0 0 0-1.818 0l-3.426 5.05a.988.988 0 0 0 .91 1.511h6.851a.988.988 0 0 0 .91-1.511Zm-8.67 6.972 3.426 5.05a1.121 1.121 0 0 0 1.818 0l3.426-5.05a.988.988 0 0 0-.909-1.511H2.574a.987.987 0 0 0-.909 1.511Z"
                  />
                </svg>
              </button>
              <button type="button" class="text-white bg-yellow-400 hover:bg-yellow-500 focus:outline-none focus:ring-4 focus:ring-yellow-300 font-medium rounded-full text-sm px-5 py-2.5 text-center mr-2 mb-2 dark:focus:ring-yellow-900">
                <NuxtLink :to="`/matakuliah/${mk.id}`"
                  ><svg class="w-6 h-6 text-gray-800 dark:text-white" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 8 14">
                    <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M7 1 1.3 6.326a.91.91 0 0 0 0 1.348L7 13" />
                  </svg>
                </NuxtLink>
              </button>
            </td>
          </tr>
        </tbody>
      </table>
    </div>
  </div> -->

  <!-- new table -->

  <div class="relative overflow-x-auto px-80 pt-5">
    <Header></Header>

    <NuxtLink to="/matakuliah/CreateData" class="flex justify-end items-center">
      <button data-tooltip-target="tooltip-document" type="button" class="inline-flex flex-col items-center justify-center px-5 hover:bg-gray-50 dark:hover:bg-gray-800 group">
        <svg class="w-5 h-5 mb-1 text-gray-500 dark:text-gray-400 group-hover:text-blue-600 dark:group-hover:text-blue-500" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="currentColor" viewBox="0 0 20 20">
          <path
            d="M.188 5H5V.13a2.96 2.96 0 0 0-1.293.749L.879 3.707c-.358.362-.617.81-.753 1.3C.148 5.011.166 5 .188 5ZM14 8a6 6 0 1 0 0 12 6 6 0 0 0 0-12Zm2 7h-1v1a1 1 0 0 1-2 0v-1h-1a1 1 0 0 1 0-2h1v-1a1 1 0 0 1 2 0v1h1a1 1 0 0 1 0 2Z"
          />
          <path d="M6 14a7.969 7.969 0 0 1 10-7.737V2a1.97 1.97 0 0 0-1.933-2H7v5a2 2 0 0 1-2 2H.188A.909.909 0 0 1 0 6.962V18a1.969 1.969 0 0 0 1.933 2h6.793A7.976 7.976 0 0 1 6 14Z" />
        </svg>
        <span class="sr-only">New document</span>
      </button>
    </NuxtLink>

    <table class="w-full text-sm text-left text-gray-500 dark:text-gray-400 mt-5">
      <thead class="text-xs text-gray-700 uppercase bg-blue-400 dark:bg-gray-700 dark:text-gray-400">
        <tr>
          <th scope="col" class="px-6 py-3">Mata kuliah</th>
          <th scope="col" class="px-6 py-3">Sks</th>
          <th scope="col" class="px-6 py-3">id</th>
          <th scope="col" class="px-6 py-3">action</th>
        </tr>
      </thead>
      <tbody>
        <tr class="bg-white border-b dark:bg-gray-800 dark:border-gray-700" v-for="mk in Matakuliah" :key="mk.id">
          <th scope="row" class="px-6 py-4 font-medium text-gray-900 whitespace-nowrap dark:text-white">{{ mk.matakuliah }}</th>
          <td class="px-6 py-3">{{ mk.sks }}</td>
          <td class="px-6 py-3">{{ mk.id }}</td>
          <td class="px-6 py-3"><a href="#" class="font-medium text-blue-600 dark:text-blue-500 hover:underline">Edit</a></td>
        </tr>
      </tbody>
    </table>
  </div>

  <!-- end table -->
  <Footer></Footer>
</template>
<script setup>
definePageMeta({
  layout: 'matkul',
});
const { data: Matakuliah } = await useFetch('https://64abc8e39edb4181202e87b6.mockapi.io/akademik/v1/matakuliah');
</script>
