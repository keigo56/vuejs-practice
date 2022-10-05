<!-- 
  Vue Exercise 1
  
  Based on your knowledge of text interpolation, v-bind and ref(), create the Dota 2 Hero Loadout based on the information given below.

  Hero Name: PUDGE
  Hero Image URL: https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/pudge.png 
  Attack Type: MELEE
  Primary Attribute: STRENGTH
  Primary Attribute Image URL: https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/icons/hero_strength.png


  Declare reactive data for each Hero property and bind to the template
 -->

<script setup></script>

<template>
  <div class="bg-[#1E1E1E] w-full h-screen px-10 py-10">
    <div class="flex items-center justify-center">
      <img
        src="https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/dota_footer_logo.png"
        class="w-40 mb-3"
        alt=""
      />
    </div>
    <div class="flex items-center justify-center mb-10">
      <h1 class="text-white font-semibold text-xl">ALL PICK</h1>
    </div>
    <div class="bg-[#1b1f2a] p-5 rounded">
      <!-- Bind to alt attribute the Hero Name -->
      <img class="rounded-md w-full" src="" alt="Hero Image" />

      <div class="flex items-center mt-3">
        <!-- Bind to alt attribute the Hero Primary Attribute -->
        <img src="" class="w-6 h-6 mr-2" alt="Hero Primary Attribute" />
        <h1 class="text-white">HERO PRIMARY ATTRIBUTE</h1>
      </div>
      <div class="flex items-center">
        <h1 class="text-white text-4xl font-semibold">HERO NAME</h1>
      </div>

      <!-- IF THE HERO ATTACK TYPE IS MELEE, APPLY text-red-900 class, if not, apply text-green-900 -->
      <p class="text-red-900">HERO ATTACK TYPE</p>

      <button
        class="
          mt-8
          bg-[#252628]
          rounded
          w-full
          p-3
          shadow
          border border-gray-800
        "
      >
        <div class="text-left">
          <h1 class="text-gray-600 font-semibold">LOCK IN</h1>
          <h1 class="text-gray-400 text-3xl">HERO NAME</h1>
        </div>
      </button>
    </div>
  </div>
</template>
