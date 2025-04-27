<template>
  <footer class="bg-[#12294A] text-white px-4 py-10 md:py-[60px]">
    <!-- Desktop Layout -->
    <div
      class="hidden md:grid grid-cols-3 lg:grid-cols-5 gap-8 max-w-[1440px] mx-auto"
    >
      <!-- Help Center -->
      <div class="">
        <h2 class="text-2xl font-medium text-white">Help Center</h2>
        <p class="mt-2 text-sm text-[#90A2BD]">If you have any questions?</p>
        <button
          class="mt-4 bg-[#3555FF] hover:opacity-75 text-white uppercase text-xs font-normal rounded-[10px] h-10 w-[200px]"
        >
          GET ANSWERS
        </button>
        <div class="flex gap-6 mt-10">
          <img
            src="/icons/telegram.svg"
            alt="Telegram"
            class="w-[30px] h-[30px]"
          >
          <img
            src="/icons/facebook.svg"
            alt="Facebook"
            class="w-[30px] h-[30px]"
          />
          <img
            src="/icons/instagram.svg"
            alt="Instagram"
            class="w-[30px] h-[30px]"
          />
          <img
            src="/icons/twitter.svg"
            alt="Twitter"
            class="w-[30px] h-[30px]"
          />
        </div>
      </div>

      <div class="space-y-5" v-for="({title, items = []}, idx) in footerNavs" :key="idx">
        <h3 class="text-sm font-medium text-white">{{ title }}</h3>
        <ul class="space-y-5 text-sm font-normal text-[#90A2BD]">
          <li v-for="(item, index) in items" :key="index">{{ item }}</li>
        </ul>
      </div>

      <!-- App Download -->
      <div class="flex flex-col gap-2 justify-start items-center">
        <button
          class="bg-[#1A3157] px-2.5 py-1.5 rounded-lg flex items-center w-full"
        >
          <img src="/icons/apple.svg" alt="Mac" class="w-[42px] h-[42px]" />
          <span
            class="flex flex-col items-start text-white text-sm font-medium"
          >
            <span>Bluechip App</span>
            <span>for Mac OS</span>
          </span>
        </button>
        <div class="flex gap-2 w-full">
          <button
            class="flex-1 bg-[#1A3157] rounded-[10px] flex flex-col items-center"
          >
            <img
              src="/icons/android.svg"
              alt="Android"
              class="w-[42px] h-[42px]"
            />
            <span class="text-sm text-[#90A2BD] font-normal">Android</span>
          </button>
          <button
            class="flex-1 bg-[#1A3157] rounded-[10px] flex flex-col items-center"
          >
            <img src="/icons/apple.svg" alt="Apple" class="w-[42px] h-[42px]" />
            <span class="text-sm text-[#90A2BD] font-normal">iOS</span>
          </button>
        </div>
      </div>
    </div>

    <!-- Mobile Layout -->
    <div class="block md:hidden max-w-md mx-auto">
      <!-- Accordions -->
      <div v-for="(section, idx) in footerNavs" :key="idx" class="mb-4">
        <button
          class="w-full bg-[#1A3157] flex justify-between items-center px-4 py-3 rounded-[10px] text-white font-medium text-sm"
          @click="toggleSection(idx)"
        >
          {{ section.title }}
          <span :class="{ 'rotate-180': openSection === idx }"
            ><svg
              xmlns="http://www.w3.org/2000/svg"
              width="18"
              height="19"
              viewBox="0 0 18 19"
              fill="none"
            >
              <path
                d="M4.34238 6.78447C4.41113 6.71572 4.49707 6.68135 4.6002 6.68135C4.70332 6.68135 4.78926 6.71572 4.85801 6.78447L9.0002 10.9267L13.1424 6.78447C13.2111 6.71572 13.2971 6.68135 13.4002 6.68135C13.5033 6.68135 13.5893 6.71572 13.658 6.78447L13.9158 7.04228C13.9846 7.11103 14.0189 7.19697 14.0189 7.3001C14.0189 7.40322 13.9846 7.48916 13.9158 7.55791L9.25801 12.2157C9.18926 12.2845 9.10332 12.3188 9.0002 12.3188C8.89707 12.3188 8.81113 12.2845 8.74238 12.2157L4.08457 7.55791C4.01582 7.48916 3.98145 7.40322 3.98145 7.3001C3.98145 7.19697 4.01582 7.11103 4.08457 7.04228L4.34238 6.78447Z"
                fill="white"
              />
            </svg>
          </span>
        </button>
        <div
          v-if="openSection === idx"
          class="bg-[#0d2344] py-4 text-gray-400 text-sm space-y-2"
        >
          <ul class="space-y-2">
            <li class="px-4 py-2 cursor-pointer hover:opacity-75" v-for="item in section.items" :key="item">{{ item }}</li>
          </ul>
        </div>
      </div>

      <p class="text-white font-medium text-sm py-5 text-center">Follow Us</p>
      <!-- Social Icons -->
      <div class="flex items-center justify-between my-6 mb-20 px-9">
        <img src="/icons/telegram.svg" alt="Telegram" class="w-9 h-9" />
        <img src="/icons/facebook.svg" alt="Facebook" class="w-9 h-9" />
        <img src="/icons/instagram.svg" alt="Instagram" class="w-9 h-9" />
        <img src="/icons/twitter.svg" alt="Twitter" class="w-9 h-9" />
      </div>

      <!-- Help Center & Apps -->
      <div class="space-y-4">
        <!-- Help Center block: responsive layout -->
        <div
          class="bg-[#18335f] p-4 rounded flex sm:flex-col sm:items-center justify-between gap-2"
        >
          <div>
            <h2 class="text-sm font-semibold">Help Center</h2>
            <p class="text-xs text-gray-400 mt-1">If you have any questions?</p>
          </div>
          <button
            class="bg-[#3555FF] hover:opacity-75 text-white text-sm font-normal py-2.5 px-4 rounded-[10px] mt-2 sm:mt-0 uppercase"
          >
            GET ANSWERS
          </button>
        </div>

        <!-- App download buttons -->
        <div class="flex gap-2">
          <button
            class="flex-1 bg-[#1A3157] py-1.5 rounded-lg flex items-center justify-center"
          >
            <img
              src="/icons/android.svg"
              alt="Android"
              class="w-[42px] h-[42px]"
            />
            <span class="flex flex-col items-start">
              <span class="text-[15px] font-medium leading-5 text-white"
                >Bluechip App</span
              >
              <span class="text-xs font-normal text-[#90A2BD]"
                >for Android</span
              >
            </span>
          </button>
          <button
            class="flex-1 bg-[#1A3157] py-1.5 rounded-lg flex items-center justify-center"
          >
            <img src="/icons/apple.svg" alt="Apple" class="w-[42px] h-[42px]" />
            <span class="flex flex-col items-start">
              <span class="text-[15px] font-medium leading-5 text-white"
                >Bluechip App</span
              >
              <span class="text-xs font-normal text-[#90A2BD]">for iOS</span>
            </span>
          </button>
        </div>
      </div>
    </div>
  </footer>
</template>

<script setup lang="ts">
import { ref } from "vue";

interface FooterNavItem {
  title: string;
  items: string[]
}

const openSection = ref<number | null>(null);

const toggleSection = (index: number) => {
  openSection.value = openSection.value === index ? null : index;
};

const footerNavs: FooterNavItem[] = [
  {
    title: "Games",
    items: ["Game 1", "Game 2", "Game 3", "Game 14"],
  },
  {
    title: "About",
    items: [
      "About Us",
      "Promotions",
      "VIP",
      "Help Center",
      "Awards & Certificates",
      "App",
    ],
  },
  {
    title: "Legal Information",
    items: [
      "General Terms & Conditions",
      "Responsible Gaming Policy",
      "Sports Betting Rules",
      "Privacy and Cookies Policy",
      "Payment Methods",
      "Limits",
    ],
  },
];
</script>
