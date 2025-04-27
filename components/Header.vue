<template>
  <header
    class="bg-[#03193A] text-white px-4 py-3 lg:py-4 flex items-center justify-center border-b border-[rgba(245,249,255,0.05)]"
  >
    <div class="flex items-center justify-between w-full max-w-[1440px]">
      <div class="flex items-center justify-start space-x-[57px]">
        <div class="flex items-center justify-start space-x-1.5 shrink-0">
          <button class="focus:outline-none">
            <img src="/icons/hambuger.svg" alt="Menu" class="w-9 h-9" />
          </button>
          <img src="/logos/logo.png" alt="Logo" class="h-[30px]" />
        </div>
        <div class="flex items-center justify-start space-x-8">
          <button class="hidden lg:block">
            <svg class="w-[30px] h-[30px]" fill="white" viewBox="0 0 24 24">
              <path
                d="M10 2a8 8 0 015.29 13.71l4 4a1 1 0 01-1.42 1.42l-4-4A8 8 0 1110 2zm0 2a6 6 0 100 12A6 6 0 0010 4z"
              />
            </svg>
          </button>
          <nav class="hidden lg:flex space-x-6 text-sm font-medium uppercase tracking-widest">
            <a v-for="{ id, href, label } in navs" :key="id" :href="href" class="hover:text-gray-300">{{ label }}</a>
          </nav>
        </div>
      </div>
      <div class="flex items-center space-x-3">
        <button
          class="bg-[#12294A] hover:opacity-75 px-3 py-2.5 rounded-[10px] text-sm leading-4 font-normal uppercase tracking-widest"
        >
          LOGIN
        </button>
        <button
          class="bg-[#01AF70] hover:opacity-75 px-3 py-2.5 rounded-[10px] text-sm leading-4 font-normal uppercase tracking-widest text-white"
        >
          REGISTRATION
        </button>
      </div>
    </div>
  </header>
</template>

<script setup lang="ts">
interface NavItems {
  id: string;
  label: string;
  href: string;
}
const navs: NavItems[] = [
  {
    id: "home",
    label: "home",
    href: "#",
  },
  {
    id: "game",
    label: "game",
    href: "#",
  },
  {
    id: "infor",
    label: "infor",
    href: "#",
  },
  {
    id: "news",
    label: "news",
    href: "#",
  },
  {
    id: "promotions",
    label: "promotions",
    href: "#",
  },
  {
    id: "vip",
    label: "vip",
    href: "#",
  },
];
</script>

<style scoped></style>
