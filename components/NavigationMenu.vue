<template>
  <div class="bg-[#03193a] py-8 px-4 lg:px-0 flex items-center justify-center">
    <!-- Desktop -->
    <div class="hidden 1440:flex gap-2 justify-center max-w-[1440px]">
      <MenuButton
        v-for="{ id, icon, isGroup, text } in desktopList"
        :key="id"
        :text="text"
        :isGroup="isGroup"
        :icon="icon"
      />
    </div>

    <!-- Mobile -->
    <div
      class="flex 1440:hidden gap-1.5 justify-center px-4 py-6 overflow-hidden"
    >
      <MenuButton
        v-for="{ id, icon, isGroup, text } in mobileList"
        :key="id"
        :text="text"
        :isGroup="isGroup"
        :icon="icon"
      />
    </div>
  </div>
</template>

<script setup lang="ts">

interface Item {
  icon: string;
  text: string;
  id: string;
  isGroup: boolean;
}
const desktopList: Item[] = [
  {
    id: "diamond-mine",
    text: "Diamond mine",
    icon: '/icons/diamond.svg',
    isGroup: false,
  },
  {
    id: "vip",
    text: "VIP",
    icon: '/icons/vip.svg',
    isGroup: false,
  },
  {
    id: "promotion",
    text: "Promotion",
    icon: '/icons/promotion.svg',
    isGroup: false,
  },
  {
    id: "hot-match",
    text: "Hot Match",
    icon: '/icons/match.svg',
    isGroup: false,
  },
  {
    id: "p2p-transaction",
    text: "P2P Transaction",
    icon: '/icons/transaction.svg',
    isGroup: false,
  },
  {
    id: "games",
    text: "Games",
    icon: '/icons/games.svg',
    isGroup: true,
  },
  {
    id: "providers",
    text: "Providers",
    icon: '/icons/providers.svg',
    isGroup: true,
  },
];

const mobileList: Item[] = [
  {
    id: "search",
    text: "Search",
    icon: '/icons/search.svg',
    isGroup: true,
  },
  {
    id: "games",
    text: "Games",
    icon: '/icons/games.svg',
    isGroup: true,
  },
  {
    id: "providers",
    text: "Providers",
    icon: '/icons/providers.svg',
    isGroup: true,
  },
];
</script>
