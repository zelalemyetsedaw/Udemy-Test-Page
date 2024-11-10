<template>
  <div class="bg-white">
    <div class="py-4 flex justify-between items-center gap-3 px-4">
      <!-- Logo -->
      <img src="https://www.udemy.com/staticx/udemy/images/v7/logo-udemy.svg" width="100" alt="udemy"
        class="w-50 h-50" />

      <!-- Categories -->
      <div class="relative" @mouseenter="showCategories = true" @mouseleave="showCategories = false">
        <p class="text-sm cursor-pointer">Categories</p>
        <div v-if="showCategories" class="absolute top-12 left-0 bg-white z-10 shadow-lg border rounded w-48">
          <ul>
            <li class="p-2 hover:bg-gray-100">Development</li>
            <li class="p-2 hover:bg-gray-100">Business</li>
            <li class="p-2 hover:bg-gray-100">Finance & Accounting</li>
            <li class="p-2 hover:bg-gray-100">IT & Software</li>
          </ul>
        </div>
      </div>

      <!-- Search Box -->
      <div class="flex items-center border border-black rounded-3xl overflow-hidden w-full max-w-lg">
        <span class="p-3 text-gray-500">
          <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5"
            stroke="currentColor" class="w-5 h-5">
            <path stroke-linecap="round" stroke-linejoin="round"
              d="M21 21l-4.35-4.35M10.5 18a7.5 7.5 0 1 1 0-15 7.5 7.5 0 0 1 0 15z" />
          </svg>
        </span>
        <input type="text" placeholder="Search for anything" class="w-full p-2 outline-none" />
      </div>

      <!-- Udemy Business -->
      <div class="relative" @mouseenter="showBusiness = true" @mouseleave="showBusiness = false">
        <p class="text-sm cursor-pointer">Udemy Business</p>
        <div v-if="showBusiness"
          class="absolute flex flex-col items-center top-12 z-10 right-0 bg-white shadow-lg border rounded w-60 py-4 px-2">
          <p class="mb-2 font-bold text-center">Get your team access to over 27,000 top Udemy courses, anytime,
            anywhere.</p>
          <button class="font-bold px-4 py-2 w-full bg-black text-white rounded"> Try Udemy Business </button>
        </div>
      </div>

      <!-- Teaching on Udemy -->
      <div class="relative" @mouseenter="showTeaching = true" @mouseleave="showTeaching = false">
        <p class="text-sm cursor-pointer">Teaching on Udemy</p>
        <div v-if="showTeaching"
          class="absolute flex flex-col items-center top-12 z-20 right-0 bg-white shadow-lg border rounded w-60 p-4">
          <p class="mb-2 font-bold">Turn what you know into an opportunity and reach millions around the world.</p>
          <button class="w-full px-4 py-2 bg-black text-white rounded font-bold"> Learn more </button>
        </div>
      </div>

      <!-- Cart Icon -->
      <div class="relative" @mouseenter="showCart = true" @mouseleave="showCart = false">
        <button class="p-2">
          <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5"
            stroke="currentColor" class="size-6">
            <path stroke-linecap="round" stroke-linejoin="round"
              d="M2.25 3h1.386c.51 0 .955.343 1.087.835l.383 1.437M7.5 14.25a3 3 0 0 0-3 3h15.75m-12.75-3h11.218c1.121-2.3 2.1-4.684 2.924-7.138a60.114 60.114 0 0 0-16.536-1.84M7.5 14.25 5.106 5.272M6 20.25a.75.75 0 1 1-1.5 0 .75.75 0 0 1 1.5 0Zm12.75 0a.75.75 0 1 1-1.5 0 .75.75 0 0 1 1.5 0Z" />
          </svg>
        </button>
        <div v-if="showCart"
          class="absolute top-14 flex flex-col items-center z-20 right-0 bg-white shadow-lg border rounded w-60 p-4">
          <p class="mb-2">Your cart is currently empty.</p>
          <button class="px-4 py-2 bg-white text-black rounded"> keep shopping </button>
        </div>
      </div>

      <!-- Login and Signup Buttons -->
      <div class="flex gap-2">
        <button class="font-bold px-4 py-2 bg-white border border-black text-black ">Login</button>
        <button class="font-bold px-4 py-2 bg-[#1C1D1F] text-white ">Signup</button>

        <!-- Browser Icon -->
        <button class="p-2 border border-black">
          <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5"
            stroke="currentColor" class="size-6">
            <path stroke-linecap="round" stroke-linejoin="round"
              d="M2.25 3h1.386c.51 0 .955.343 1.087.835l.383 1.437M7.5 14.25a3 3 0 0 0-3 3h15.75m-12.75-3h11.218c1.121-2.3 2.1-4.684 2.924-7.138a60.114 60.114 0 0 0-16.536-1.84M7.5 14.25 5.106 5.272M6 20.25a.75.75 0 1 1-1.5 0 .75.75 0 0 1 1.5 0Zm12.75 0a.75.75 0 1 1-1.5 0 .75.75 0 0 1 1.5 0Z" />
          </svg>

        </button>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';

const showCategories = ref(false);
const showBusiness = ref(false);
const showTeaching = ref(false);
const showCart = ref(false)
</script>
