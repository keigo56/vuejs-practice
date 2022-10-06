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

<script setup>
import { ref } from 'vue';
let heroName = ref('PUDGE');
let heroImageURL = ref(
  'https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/pudge.png'
);
let heroAttackType = ref('MELEE');
let heroPrimaryAttribute = ref('STRENGTH');
let heroPrimaryAttributeImageURL = ref(
  'https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/icons/hero_strength.png'
);

let heroSkills = ref([
  {
    name: 'MEAT HOOK',
    description:
      "Launches a bloody hook toward a unit or location. The hook will snag the first unit it encounters, dragging the unit back to Pudge, killing it if it's a non-ancient creep and dealing damage if it is an enemy otherwise.",
    imgSrc:
      'https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/abilities/pudge_meat_hook.png',
  },
  {
    name: 'ROT',
    description:
      'A toxic cloud that deals intense damage and slows movement--harming not only enemy units but Pudge himself.',
    imgSrc:
      'https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/abilities/pudge_rot.png',
  },
  {
    name: 'FLESH HEAP',
    description:
      'Gives Pudge a guaranteed damage block against all types of attack. Passively grants bonus strength that increases each time Pudge kills an enemy Hero or it dies in his vicinity.  Flesh Heap is retroactive, meaning it can gain charges before it is skilled, which then become active.',
    imgSrc:
      'https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/abilities/pudge_flesh_heap.png',
  },
  {
    name: 'DISMEMBER',
    description:
      'CHANNELED - Pudge chows down on an enemy unit, disabling it and dealing damage over time. Pudge gets healed for the same amount he damages. Lasts longer on creeps.',
    imgSrc:
      'https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/abilities/pudge_dismember.png',
  },
]);

const radiantHeroes = ref([
  {
    name: 'ANTI-MAGE',
    imgSrc:
      'https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/antimage.png',
  },
  {
    name: 'Alchemist',
    imgSrc:
      'https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/alchemist.png',
  },
  {
    name: 'PUDGE',
    imgSrc:
      'https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/pudge.png',
  },
  {
    name: 'JUGGERNAUT',
    imgSrc:
      'https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/juggernaut.png',
  },
  {
    name: 'NECROPHOS',
    imgSrc:
      'https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/necrolyte.png',
  },
]);

const direHeroes = ref([
  {
    name: 'Invoker',
    imgSrc:
      'https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/invoker.png',
  },
  {
    name: 'Drow Ranger',
    imgSrc:
      'https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/drow_ranger.png',
  },
  {
    name: 'Legion Commander',
    imgSrc:
      'https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/legion_commander.png',
  },
  {
    name: 'Shadow Shaman',
    imgSrc:
      'https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/shadow_shaman.png',
  },
  {
    name: 'Sand King',
    imgSrc:
      'https://cdn.cloudflare.steamstatic.com/apps/dota2/images/dota_react/heroes/sand_king.png',
  },
]);
</script>

<template>
  <!-- HERO LOADOUT  -->
  <div class="bg-[#1E1E1E] w-full px-10 py-10">
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
      <div class="flex items-center">
        <img class="rounded-md w-full" :src="heroImageURL" :alt="heroName" />
      </div>

      <div class="flex items-center mt-3">
        <!-- Bind to alt attribute the Hero Primary Attribute -->
        <img
          :src="heroPrimaryAttributeImageURL"
          class="w-6 h-6 mr-2"
          :alt="heroPrimaryAttribute"
        />
        <h1 class="text-white">{{ heroPrimaryAttribute }}</h1>
      </div>
      <div class="flex items-center">
        <h1 class="text-white text-4xl font-semibold">{{ heroName }}</h1>
      </div>

      <!-- IF THE HERO ATTACK TYPE IS MELEE, APPLY text-red-900 class, if not, apply text-green-900 -->
      <p
        :class="heroAttackType === 'MELEE' ? 'text-red-900' : 'text-green-900'"
      >
        {{ heroAttackType }}
      </p>

      <div class="mt-4 border-t border-gray-700">
        <h1 class="text-gray-400 font-semibold text-xl mt-4">ABILITIES</h1>
      </div>
      <div class="flex items-center space-x-3 mt-5">
        <div v-for="skill in heroSkills">
          <img
            :src="skill.imgSrc"
            class="w-full hover:ring hover:ring-gray-500 cursor-pointer"
            alt=""
          />
        </div>
      </div>

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
          <h1 class="text-gray-400 text-3xl">{{ heroName }}</h1>
        </div>
      </button>
    </div>
  </div>

  <!-- HEROES -->
  <div class="bg-zinc-900 pb-10">
    <div class="flex justify-between space-x-4">
      <!-- RADIANT HEROES -->
      <div>
        <div class="pl-10 py-5">
          <h1
            class="
              font-[cinzel] font-semibold
              text-xl text-green-300 text-radiant
            "
          >
            THE RADIANT
          </h1>
        </div>
        <div
          class="
            pl-10
            flex-col flex
            items-center
            justify-around
            w-full
            space-y-2
          "
        >
          <div
            :class="radiantHero.name === heroName ? 'bg-emerald-600' : ''"
            class="bg-[#1b1f2a] rounded p-2 cursor-pointer w-full"
            v-for="radiantHero in radiantHeroes"
          >
            <img
              class="w-full"
              :src="radiantHero.imgSrc"
              :alt="radiantHero.name"
            />
          </div>
        </div>
      </div>

      <!-- DIRE HEROES -->
      <div>
        <div class="px-10 py-5">
          <h1
            class="
              font-[cinzel] font-semibold
              text-xl text-red-300 text-dire text-right
            "
          >
            THE DIRE
          </h1>
        </div>
        <div
          class="
            pr-10
            flex-col flex
            items-center
            justify-around
            w-full
            space-y-2
          "
        >
          <div
            class="bg-[#1b1f2a] rounded p-2 cursor-pointer w-full"
            v-for="direHero in direHeroes"
          >
            <img class="w-full" :src="direHero.imgSrc" :alt="direHero.name" />
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
