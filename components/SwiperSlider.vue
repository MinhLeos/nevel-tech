<template>
  <Swiper
    :modules="[Autoplay]"
    :autoplay="autoplay"
    :loop="true"
    :centered-slides="true"
    :breakpoints="breakpoints"
    class="h-[430px] w-full swiper-container"
    @swiper="onSwiper"
    @slideChange="onSlideChange"
  >
    <SwiperSlide
      v-for="{
        background,
        btnLabel,
        heading,
        image,
        description,
        label,
        id,
      } in slides"
      :key="id"
      class="transition-all duration-500 ease-in-out cursor-grab"
    >
      <div
        :class="[
          'h-full w-full rounded-xl relative flex flex-col sm:flex-row justify-end sm:px-3 slide-container',
          background,
        ]"
      >
        <div
          class="absolute top-2.5 right-2.5 sm:top-5 sm:right-5 p-1 opacity-75"
        >
          <svg
            class="w-4 h-4"
            xmlns="http://www.w3.org/2000/svg"
            width="17"
            height="17"
            viewBox="0 0 17 17"
            fill="#fff"
          >
            <path
              d="M8.2002 1.92773C9.09082 1.92773 9.93457 2.0918 10.7314 2.41992C11.5127 2.76367 12.2002 3.23242 12.7939 3.82617C13.3877 4.41992 13.8564 5.10742 14.2002 5.88867C14.5283 6.68555 14.6924 7.5293 14.6924 8.41992C14.6924 9.31055 14.5283 10.1543 14.2002 10.9512C13.8564 11.7324 13.3877 12.4199 12.7939 13.0137C12.2002 13.6074 11.5127 14.0762 10.7314 14.4199C9.93457 14.748 9.09082 14.9121 8.2002 14.9121C7.30957 14.9121 6.46582 14.748 5.66895 14.4199C4.8877 14.0762 4.2002 13.6074 3.60645 13.0137C3.0127 12.4199 2.54395 11.7324 2.2002 10.9512C1.87207 10.1543 1.70801 9.31055 1.70801 8.41992C1.70801 7.5293 1.87207 6.68555 2.2002 5.88867C2.54395 5.10742 3.0127 4.41992 3.60645 3.82617C4.2002 3.23242 4.8877 2.76367 5.66895 2.41992C6.46582 2.0918 7.30957 1.92773 8.2002 1.92773ZM8.2002 0.427734C7.09082 0.427734 6.05176 0.630859 5.08301 1.03711C4.11426 1.45898 3.2666 2.0332 2.54004 2.75977C1.81348 3.48633 1.23926 4.33398 0.817383 5.30273C0.411133 6.27148 0.208008 7.31055 0.208008 8.41992C0.208008 9.5293 0.411133 10.5684 0.817383 11.5371C1.23926 12.5059 1.81348 13.3535 2.54004 14.0801C3.2666 14.8066 4.11426 15.3809 5.08301 15.8027C6.05176 16.209 7.09082 16.4121 8.2002 16.4121C9.30957 16.4121 10.3486 16.209 11.3174 15.8027C12.2861 15.3809 13.1338 14.8066 13.8604 14.0801C14.5869 13.3535 15.1611 12.5059 15.583 11.5371C15.9893 10.5684 16.1924 9.5293 16.1924 8.41992C16.1924 7.31055 15.9893 6.27148 15.583 5.30273C15.1611 4.33398 14.5869 3.48633 13.8604 2.75977C13.1338 2.0332 12.2861 1.45898 11.3174 1.03711C10.3486 0.630859 9.30957 0.427734 8.2002 0.427734ZM8.36426 7.08398H7.87207C7.73145 7.08398 7.61035 7.13477 7.50879 7.23633C7.40723 7.33789 7.35645 7.45117 7.35645 7.57617V11.9121C7.35645 12.0527 7.40723 12.1738 7.50879 12.2754C7.61035 12.377 7.73145 12.4277 7.87207 12.4277H8.36426C8.50488 12.4277 8.62207 12.377 8.71582 12.2754C8.80957 12.1738 8.85645 12.0527 8.85645 11.9121V7.57617C8.85645 7.45117 8.80957 7.33789 8.71582 7.23633C8.62207 7.13477 8.50488 7.08398 8.36426 7.08398ZM8.85645 4.92773V5.25586C8.85645 5.39648 8.80957 5.51367 8.71582 5.60742C8.62207 5.70117 8.50488 5.74805 8.36426 5.74805H7.87207C7.73145 5.74805 7.61035 5.70117 7.50879 5.60742C7.40723 5.51367 7.35645 5.39648 7.35645 5.25586V4.92773C7.35645 4.78711 7.40723 4.66602 7.50879 4.56445C7.61035 4.46289 7.73145 4.41211 7.87207 4.41211H8.36426C8.50488 4.41211 8.62207 4.46289 8.71582 4.56445C8.80957 4.66602 8.85645 4.78711 8.85645 4.92773Z"
              fill="white"
            />
          </svg>
        </div>
        <div
          class="h-3/4 sm:h-full w-full sm:w-1/2 flex flex-col space-y-3 items-center justify-center text-white"
        >
          <p
            v-if="!!label"
            class="rounded-full py-1 px-10 text-center bg-[#FFFFFF1A] text-xs font-semibold xl:text-xl"
          >
            {{ label }}
          </p>
          <h2
            class="w-64 2xl:w-[340px] text-center font-medium text-2xl 2xl:text-4xl"
          >
            {{ heading }}
          </h2>
          <button
            class="cursor-pointer uppercase w-[250px] 2xl:w-[340px] h-[50px] flex items-center justify-center bg-[#FF0960] text-white rounded-[10px] font-semibold text-base leading-4"
          >
            {{ btnLabel }}
          </button>
          <p
            v-if="!!description"
            class="text-center w-64 2xl:w-[340px] text-xs lg:text-sm leading-[18px] font-normal"
          >
            {{ description }}
          </p>
        </div>
        <div
          class="w-52 sm:w-1/2 absolute -top-12 left-1/2 translate-x-[-50%] sm:relative sm:top-auto sm:left-auto sm:translate-x-0"
        >
          <img
            :src="image"
            :alt="heading"
            class="w-full h-full object-contain"
          />
        </div>
      </div>
    </SwiperSlide>
    <div class="sm:hidden flex items-center justify-center space-x-1.5 mt-3">
      <span
        v-for="({ id }, idx) in slides"
        :key="id"
        :class="[
          'w-1.5 h-1.5 rounded-full',
          activeSlide === idx ? 'bg-[#FFFFFF]' : 'bg-[#FFFFFF66]',
        ]"
      />
    </div>
  </Swiper>
</template>

<script setup lang="ts">
import { ref, onMounted } from "vue";
import { Swiper, SwiperSlide } from "swiper/vue";
import { Autoplay } from "swiper/modules";
import "swiper/css";
import "swiper/css/autoplay";
import "swiper/css/bundle";

interface SlideItem {
  id: string;
  background: string;
  heading: string;
  description?: string;
  label?: string;
  btnLabel: string;
  image: string;
}

const autoplay = {
  delay: 3000111,
  disableOnInteraction: false,
};

const breakpoints = {
  0: {
    slidesPerView: 1,
    centeredSlides: true,
    spaceBetween: 10,
  },
  1024: {
    slidesPerView: 1.5,
    centeredSlides: true,
    spaceBetween: 10,
  },
  1280: {
    slidesPerView: 1.75,
    centeredSlides: true,
    spaceBetween: 10,
  },
  1440: {
    slidesPerView: 1.9,
    centeredSlides: true,
    spaceBetween: 10,
  },
  1560: {
    slidesPerView: 2,
    centeredSlides: true,
    spaceBetween: 10,
  },
};

const swiperRef = ref<typeof Swiper | null>(null);
const activeSlide = ref(0)
let slides = reactive<SlideItem[]>([]);

const onSwiper = (swiper: typeof Swiper) => {
  swiperRef.value = swiper;
};

const onSlideChange = (swiper: typeof Swiper) => {
  activeSlide.value = swiper.realIndex ?? 0
}

onMounted(() => {
  slides = [
    {
      id: "exclusive-tournament",
      background:
        "bg-[linear-gradient(180deg,_#147261_0%,_#082C25_101.56%)] md:bg-[linear-gradient(65deg,_#147261_27.03%,_#082C25_78.3%)]",
      heading: "Piggy Christmas Tap: €35,000 For Your Wins",
      label: "Exclusive Tournament",
      btnLabel: "JOIN AND WIN",
      image: "/images/exclusive-tournament.png",
    },
    {
      id: "cash-back",
      background:
        "bg-[linear-gradient(180deg,_#284DCE_0%,_#0C1741_101.56%)] md:bg-[linear-gradient(65deg,_#284DCE_27.03%,_#0C1741_78.3%)]",
      heading: "Win or Get Back up to €100",
      description:
        "See your best cashback offers for Slots, Live Games, and Crash Games. Play and get your money back daily!",
      label: "CashBack",
      btnLabel: "Discover More",
      image: "/images/cash-back.png",
    },
    {
      id: "app",
      background:
        "bg-[linear-gradient(180deg,_#284DCE_0%,_#0C1741_101.56%)] md:bg-[linear-gradient(65deg,_#284DCE_27.03%,_#0C1741_78.3%)]",
      heading: "Install Our App: Play fast and secure",
      description: "Take your mobile app to the next level!",
      btnLabel: "Get it now",
      image: "/images/app.png",
    },
    {
      id: "trade",
      background:
        "bg-[linear-gradient(180deg,_#0C477C_0%,_#590FB7_101.56%)] md:bg-[linear-gradient(65deg,_#26002F_27.03%,_#590FB7_78.3%)]",
      heading: "Up to €1,000 / 1 BTC",
      description:
        "Increase your chances of winning big with a 400% welcome bonus (up to €1,000 / 1 BTC). New players only. Bonus terms apply.",
      btnLabel: "Get it now",
      image: "/images/trade.png",
    },
    {
      id: "sport-welcome-pack",
      background:
        "bg-[linear-gradient(180deg,_#0B467B_0%,_#041B2E_101.56%)] md:bg-[linear-gradient(65deg,_#0B467B_27.03%,_#041B2E_78.3%)]",
      heading: "Up to 300%",
      description:
        "Boost your balance by getting a €60 FreeBet for the first 3 deposits to win with favs at BlueChip. New players only.",
      label: "Sport Welcome Pack",
      btnLabel: "GET NOW",
      image: "/images/sport-welcome-pack.png",
    },
  ];
  const swiper = swiperRef.value;
  swiper?.autoplay?.stop?.();
  setTimeout(() => {
    swiper?.autoplay?.start?.();
  }, 0);
});
</script>

<style scoped>
.swiper-slide {
  opacity: 0.5;
  transform: scale(0.85);
  transition: all 0.3s ease;
  width: auto;
  perspective: 1000px;
}

.swiper-slide-active {
  opacity: 1;
  transform: scale(1);
}

.swiper-slide > .slide-container {
  transform: rotateX(-5deg) scale(1);
  transform-style: preserve-3d;
  perspective: 1000px;
  transition: transform 0.3s ease;
}
.swiper-slide-active > .slide-container {
  transform: rotateX(5deg) scale(1);
  transform-style: preserve-3d;
  perspective: 1000px;
  transition: transform 0.3s ease;
}

.swiper-container {
  padding: 20px 10px;
  overflow: hidden;
}

.swiper-wrapper {
  align-items: center;
}

@media screen and (min-width: 768px) {
  .swiper-slide > .slide-container {
    transform: rotateX(5deg) scale(1);
  }
  .swiper-slide-active > .slide-container {
    transform: rotateX(-5deg) scale(1);
  }
}
</style>
