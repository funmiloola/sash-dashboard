<script setup>
import { ref } from "vue";
import icon1 from "../assets/Icons/material-symbols--dashboard-rounded.svg";
import icon2 from "../assets/Icons/codicon--arrow-swap (1).svg";
import icon3 from "../assets/Icons/ic--outline-people.svg";
import icon4 from "../assets/Icons/mingcute--message-2-line.svg";
import icon5 from "../assets/Icons/ph--bag.svg";
import icon6 from "../assets/Icons/iconamoon--invoice-thin.svg";
import icon7 from "../assets/Icons/carbon--analytics.svg";
import icon8 from "../assets/Icons/mdi--dots-square.svg";
import icon9 from "../assets/Icons/clarity--beta-line.svg";
import icon10 from "../assets/Icons/material-symbols-light--settings-outline.svg";
import icon11 from "../assets/Icons/arcticons--security.svg";
import icon12 from "../assets/Icons/material-symbols-light--help-outline.svg";

const sidebar = ref([
  {
    img: icon1,
    name: "Dashboard",
  },
  {
    img: icon2,
    name: "Payment",
  },
  {
    img: icon3,
    name: "Customers",
  },
  {
    img: icon4,
    name: "Message",
    figure: "8",
  },
]);
const tools = ref([
  { img: icon5, name: "Product" },
  { img: icon6, name: "Invoice" },
  { img: icon7, name: "Analytic" },
  { img: icon8, name: "Automation" },
]);
const settings = ref([
  { img: icon10, name: "Settings" },
  { img: icon11, name: "Security" },
  { img: icon12, name: "Help" },
]);
const props = defineProps({
  toggleSidebar: Function,
});
</script>
<template>
  <div class="w-1/4">
    <div
      class="xl:hidden flex-col gap-8 fixed bg-white h-full left-2  z-40"
    >
    <div class="border-b-1 border-[#c1c4c4]">
      <div class="py-6">
        <div class="flex justify-between items-center pl-2 pr-2 sm:pl-4 sm:pr-2">
          <div class="flex gap-1 items-center">
            <img
              src="../assets/Icons/arcticons--x-icon-changer.svg"
              alt=""
              class="w-4 h-4 sm:w-8 sm:h-8" @click="props.toggleSidebar"
            />
           <a href="/" class=""> <p class="sm:text-2xl text-lg text-[#5347CE] sm:font-semibold">Nexus</p>
            </a>
          </div>
          <div>
            <img
              src="../assets/Icons/system-uicons--enter-alt.svg"
              alt=""
              class="sm:w-6 sm:h-6 w-3 h-3"
            />
          </div>
        </div>
      </div>
    </div>
    <div class="pb-8 border-b-1 border-[#c1c4c4]">
      <h2 class="pl-4 pt-4 text-[#c1c4c4]"><a href="">GENERAL</a></h2>
      <div
        v-for="(item, index) in sidebar"
        :key="index"
        class="flex  items-center gap-1 pt-2 pl-3 pr-2"
      >
        <img :src="item.img" alt="" class="w-4 h-4" />
        <div class="flex gap-12 items-center">
        <p><a href="">{{ item.name }}</a></p>
        <!-- <p class=""><a href="">{{ item.figure }}</a></p> -->
        </div>
      </div>
    </div>
    <div class="pb-8 border-b-1 border-[#c1c4c4]">
        <h3 class="text-[#c1c4c4] pt-4 pl-3"><a href="">TOOLS</a></h3>
        <div v-for="(tool,index) in tools" :key="index" class="flex items-center gap-2 pl-3 pt-2">
            <img :src="tool.img" alt="" class="w-4 h-4"/>
            <p><a href="">{{tool.name}}</a></p>
        </div>
    </div>
    <div class="pb-20 ">
        <h4 class="text-[#c1c4c4] pt-4 pl-3"><a href="">SUPPORT</a></h4>
        <div v-for="(setting,index) in settings" :key="index" class="flex items-center gap-2 pl-3 pt-2">
            <img :src="setting.img" alt="" class="w-4 h-4">
            <p><a href="">{{setting.name}}</a></p>
        </div>
    </div>
    <div>
    <div class="flex justify-between items-center pr-6 pl-2 border border-[#eeeeee] bg-[#eeeeee] mx-2 mb-4 py-2.5 rounded-lg">
        <div class="flex flex-col sm:flex-row items-center justify-center gap-2">
            <img src="../assets/Icons/mynaui--dots-square-solid.svg" alt=" " class="w-5 h-5 md:w-10 md:h-10">
            <div>
                <p class="text-sm md:text-lg">Team</p>
                <p class="font-normal md:font-semibold">Marketing</p>
            </div>
        </div>
        <div class="flex flex-col items-center ">
            <img src="../assets/Icons/iconamoon--arrow-up-2-thin.svg" alt="">
            <img src="../assets/Icons/oui--arrow-down.svg" alt="">
        </div>
    </div>
    <div class="border border-[#c1c4c4] mx-2 rounded-lg text-center py-2 font-semibold cursor-pointer">Upgrade Plan</div>
    </div>
    <div class="border-t-1 border-[#c1c4c4] text-center pt-4 pb-6 mt-4 text-[#c1c4c4]">@2023Nexus.io Inc.</div>
    </div>
  </div>
</template>
<style scoped>
</style>