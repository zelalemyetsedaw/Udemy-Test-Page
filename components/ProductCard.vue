<template>
    <div class="w-[341px] absolute right-16 bg-white top-0 z-10 m-10 border border-white shadow-lg">
      <!-- Image Section -->
      <div> 
        <img src="../public/video.png" alt="Video" /> 
      </div>
      
      <!-- Tabs Section (Personal and Teams) -->
      <div class="flex">
        <!-- Personal Tab -->
        <p 
          class="w-1/2 p-3 border-b-2 text-center font-bold cursor-pointer" 
          :class="{ 'border-b-black': activeTab === 'personal', 'border-hidden': activeTab !== 'personal' }" 
          @click="activeTab = 'personal'">
          Personal
        </p>
        
        <!-- Teams Tab -->
        <p 
          class="w-1/2 p-3 border-b-2 text-center cursor-pointer" 
          :class="{ 'border-b-black': activeTab === 'teams', 'border-hidden': activeTab !== 'teams' }" 
          @click="activeTab = 'teams'">
          Teams
        </p>
      </div>
      
      <!-- Content Section -->
      <div class="p-5">
        <h1 class="font-bold text-xl">Subscribe to Udemy’s top <br /> courses</h1>
        <p class="text-sm pb-4"> 
          Get this course, plus 12,000+ of our top-rated courses, with Personal Plan. 
          <a class="font-bold border-b-2 text-[#A435F0]">Learn more</a>
        </p>
        
        <!-- Button Section -->
        <button class="p-3 w-full text-white text-lg font-bold bg-[#A435F0]">
          Try personal plan for free
        </button>
        
        <!-- Content for Personal -->
        <div v-if="activeTab === 'personal'">
          <p class="pt-2 text-xs text-center text-gray-500 w-3/4 m-auto"> Starting at $10.00 per month after trial </p>
          <p class="pt-2 text-xs text-center text-gray-500 w-3/4 m-auto">Cancel anytime</p>
          
          <!-- Or Divider -->
          <div class="flex pt-4 items-center justify-center space-x-2">
            <div class="flex-1 border-t border-gray-300"></div>
            <span class="text-sm text-gray-500">or</span>
            <div class="flex-1 border-t border-gray-300"></div>
          </div>
          
          <!-- Price Section -->
          <p class="text-xl font-bold py-4"> $54.99 </p>
          
          <!-- Add to Cart Button -->
          <button class="p-3 border border-black w-full font-bold"> Add to cart</button>
          
          <!-- Guarantee and Access Information -->
          <p class="text-xs w-3/4 text-gray-500 m-auto text-center pt-2"> 30-Day Money-Back Guarantee </p>
          <p class="text-xs w-3/4 text-gray-500 m-auto text-center pt-2">Full Lifetime Access</p>
          
          <!-- Share, Gift, Coupon Section -->
          <div class="flex text-base pt-3 font-bold justify-between">
            <p class="border border-b-[#A435F0]"> share </p>
            <p class="border border-b-[#A435F0]"> gift this course </p>
            <p class="border border-b-[#A435F0]"> Apply coupon </p>
          </div>
        </div>
        
        <!-- Content for Teams -->
        <div v-if="activeTab === 'teams'">
          <ul class="text-sm flex flex-col gap-2 pt-4  text-gray-500">
            <li>For teams of 2 or more users</li>
            <li>For teams of 2 or more users</li>
            <li>For teams of 2 or more users</li>
            <li>For teams of 2 or more users</li>
          </ul>
        </div>
      </div>
    </div>
  </template>
  
  <script setup>
  import { ref } from 'vue'
  
  // Reactive property to track the active tab
  const activeTab = ref('personal')
  </script>
  
  
  