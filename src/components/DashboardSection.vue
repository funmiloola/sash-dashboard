<script setup>
import { ref } from "vue";
import icon1 from "../assets/Icons/weui--eyes-on-outlined.svg";
import icon2 from "../assets/Icons/material-symbols-light--error-outline.svg";
import icon3 from "../assets/Icons/material-symbols-light--delete-outline.svg";
import icon4 from "../assets/Icons/hugeicons--stop-circle.svg";
import icon5 from "../assets/Icons/guidance--up-right-arrow.svg";
import icon6 from "../assets/Icons/guidance--down-right-arrow.svg";
const percentages = ref([
  {
    img: icon1,
    name: "Page Views",
    icon: icon2,
    amount: "12,450",
    perc: "15.8%",
    icn: icon5,
  },
  {
    img: icon3,
    name: "Total Revenue",
    icon: icon2,
    amount: "$365.95",
    perc: "34.0%",
    icn: icon6,
  },
  {
    img: icon4,
    name: "Bounce Rate",
    icon: icon2,
    amount: "86.5%",
    perc: "24.25%",
    icn: icon5,
  },
]);
import { onMounted } from "vue";
import Chart from "chart.js/auto";

const donutChart = ref(null);

const integrations = [
  {
    name: "Stripe",
    type: "Finance",
    rate: 40,
    profit: "650.00",
    icon: "https://img.icons8.com/ios-filled/50/stripe.png",
  },
  {
    name: "Zapier",
    type: "CRM",
    rate: 80,
    profit: "720.50",
    icon: "https://img.icons8.com/color/48/zapier.png",
  },
  {
    name: "Shopify",
    type: "Marketplace",
    rate: 20,
    profit: "432.25",
    icon: "https://img.icons8.com/color/48/shopify.png",
  },
];

onMounted(() => {
  new Chart(donutChart.value.getContext("2d"), {
    type: "doughnut",
    data: {
      labels: ["Website", "Mobile App", "Other"],
      datasets: [
        {
          data: [374.82, 241.6, 213.42],
          backgroundColor: ["#5347CE", "#3fa9f5", "#c1c4c4"],
          borderWidth: 4,
          cutout: "70%",
        },
      ],
    },
    options: {
     circumference: 180,     
      rotation: -90,       
      plugins: {
        legend: { display: false },
      },
    },
  });
});
const props = defineProps({
  toggleSidebar: {
    type: Function,
    required: true,
  },
  showIcon:{
    type:Boolean
  }
})
</script>
<template>
  <div class="border border-white shadow-xl">
    <div class="border-b-1 border-[#c1c4c4]">
      <div class="flex items-center md:justify-between gap-4">
        <div class=" block md:hidden  cursor-pointer  " @click="props.toggleSidebar" >
          <img src="../assets/Icons/solar--hamburger-menu-linear.svg" alt="" class="w-12 h-12 "  >
        </div>
        <div
          class="flex items-center gap-0.5 border border-[#c1c4c4] ml-4 pl-2 rounded-lg hover:bg-gray-100 cursor-pointer"
        >
          <img
            src="../assets/Icons/material-symbols-light--search.svg"
            alt=""
            class="w-4 h-4"
          />
          <input
            class="text-[#c1c4c4] pr-0 md:pr-24 py-1 outline-none hover:bg-gray-100 cursor-pointer"
            placeholder="Search"
          />
        </div>
        <div class="flex gap-5 items-center">
          <div class="flex flex-col md:flex-row md:gap-4">
            <img
              src="../assets/Icons/ph--bag.svg"
              alt=""
              class="w-4 h-4 cursor-pointer hover:bg-gray-100"
            />
            <img
              src="../assets/Icons/bitcoin-icons--bell-outline.svg"
              alt=""
              class="w-5 h-5 cursor-pointer hover:bg-gray-100"
            />
            <img
              src="../assets/Icons/tabler--circle-dot.svg"
              alt=""
              class="w-4 h-4 cursor-pointer hover:bg-gray-100"
            />
          </div>
          <div
            class="flex items-center gap-2 pr-4 md:pr-15 pl-4 my-2 border-l border-[#c1c4c4]"
          >
            <div>
              <a href=""
                ><img
                  src="../assets/images/image-avatar.png"
                  alt=""
                  class="w-4 h-4 sm:w-8 sm:h-8"
              /></a>
            </div>
            <div>
              <p class="font-semibold text-sm md:text-xl">
                <a href="" class="">Young Alaska</a>
              </p>
              <p class="text-sm md:text-xl">Business</p>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div
      class="flex flex-col gap-3 md:flex-row md:items-center justify-between p-6 bg-[#f3f9f9]"
    >
      <div>
        <h2 class="text-2xl">Dashboard</h2>
      </div>
      <div class="hidden md:flex items-center gap-1.5">
        <div class="flex items-center">
          <div
            class="flex items-center border gap-1 px-2 py-1 bg-white rounded-s-lg border-[#c1c4c4] cursor-pointer"
          >
            <img
              src="../assets/Icons/uit--calender.svg"
              alt=""
              class="w-5 h-5"
            />
            <p>Oct18-Nov18</p>
          </div>
          <div
            class="flex items-center border gap-1 px-2 py-1 bg-white rounded-e-lg border-[#c1c4c4] cursor-pointer"
          >
            <p>Monthly</p>
            <img
              src="../assets/Icons/oui--arrow-down.svg"
              alt=""
              class="w-5 h-5"
            />
          </div>
        </div>
        <div
          class="flex items-center border gap-1 px-2 py-1 bg-white rounded-lg border-[#c1c4c4] cursor-pointer"
        >
          <img
            src="../assets/Icons/mynaui--filter-solid.svg"
            alt=""
            class="w-5 h-5"
          />
          <p>Filter</p>
        </div>
        <div
          class="flex items-center border gap-1 px-2 py-1 bg-white rounded-lg border-[#c1c4c4] cursor-pointer"
        >
          <img
            src="../assets/Icons/system-uicons--enter-alt.svg"
            alt=""
            class="w-5 h-5"
          />
          <p>Export</p>
        </div>
      </div>
    </div>
    <div
      class="bg-[#f3f9f9] flex flex-col md:flex-row justify-between items-center gap-2 px-6 pb-6"
    >
      <div
        v-for="(item, index) in percentages"
        :key="index"
        class="border border-[#c1c4c4] px-4 py-3 w-full md:w-1/3 bg-white rounded-lg"
      >
        <div class="flex justify-between items-center">
          <div class="flex gap-2">
            <img
              :src="item.img"
              alt=""
              class="w-6 h-6 bg-[#f3f9f9] border px-1 py-1 border-[#f3f9f9]"
            />
            <p class="font-semibold">{{ item.name }}</p>
          </div>
          <div>
            <img :src="item.icon" alt="" />
          </div>
        </div>
        <div class="flex gap-2 pt-3">
          <p class="text-lg lg:text-xl font-semibold">{{ item.amount }}</p>
          <div
            :class="
              index === 1
                ? 'flex items-center border border-[#f8dff1] bg-[#f8dff1] px-1 rounded'
                : 'flex items-center border border-[#dff8f8] bg-[#dff8f8] px-1 rounded'
            "
          >
            <p :class="index === 1 ? 'text-[#f590d9]' : 'text-[#96e8e8]'">
              {{ item.perc }}
            </p>
            <img :src="item.icn" alt="" class="w-4 h-3" />
          </div>
        </div>
      </div>
    </div>
    <section class="bg-[#f3f9f9] flex flex-col lg:flex-row gap-6 px-6">
      <!-- Sales Overview -->
      <div class="bg-white rounded-xl shadow p-6 flex-1">
        <div class="flex flex-col gap-3 sm:flex-row justify-between items-center mb-4">
          <div class="flex items-center gap-2">
            <img
              src="../assets/Icons/material-symbols--bar-chart-rounded.svg"
              alt=""
            />
            <h3 class="font-semibold">Sales Overview</h3>
          </div>
          <div class="flex gap-2">
            <div class="flex items-center gap-1 px-2 bg-[#f3f9f9]">
              <img
                src="../assets/Icons/mynaui--filter-solid.svg"
                alt=""
                class="w-4 h-4"
              />
              <button class="text-sm hover:text-gray-600 cursor-pointer">
                Filter
              </button>
            </div>
            <div class="flex items-center gap-1 px-2 bg-[#f3f9f9]">
              <img
                src="../assets/Icons/fluent--arrow-sort-20-regular.svg"
                alt=""
                class="w-4 h-4"
              />
              <button class="hover:text-gray-600 cursor-pointer text-sm">
                Sort
              </button>
            </div>
            <div class="bg-[#f3f9f9]">
              <img src="../assets/Icons/mynaui--dots.svg" alt="" />
            </div>
          </div>
        </div>
        <p class="text-2xl font-semibold">$9,257.51</p>
        <div class="flex gap-2 items-center pt-2">
          <div
            class="flex flex-col sm:flex-row items-center border border-[#dff8f8] bg-[#dff8f8] px-auto sm:px-1 rounded"
          >
            <p class="text-[#96e8e8]">15.5%</p>
            <img
              src="../assets/Icons/guidance--up-right-arrow.svg"
              alt=""
              class="w-4 h-3"
            />
          </div>
          <p class="text-gray-400">+$143.50 <span class="text-sm">Increased</span></p>
        </div>
        <!-- Bar chart -->
        <div class="flex justify-between items-end h-40 mt-6">
          <!-- Oct -->
          <div class="flex flex-col items-center">
            <div class="flex flex-col justify-end gap-1 w-10 sm:w-20 h-26">
              <div class="bg-[#16C8C7] h-2 rounded"></div>
              <div class="bg-[#23bdbd] h-4 rounded"></div>
              <div class="bg-[#4896FE] h-8 rounded"></div>
              <div class="bg-[#887CFD] h-10 rounded"></div>
              <div class="bg-[#5347CE] h-12 rounded"></div>
            </div>
            <p class="text-xs mt-1">$2,988.20</p>
            <p class="text-xs text-gray-500">Oct</p>
          </div>

          <!-- Nov -->
          <div class="flex flex-col items-center">
            <div class="flex flex-col justify-end gap-1 w-10 sm:w-20 h-20">
              <div class="bg-[#16C8C7] h-18 rounded"></div>
              <div class="bg-[#23bdbd] h-22 rounded"></div>
              <div class="bg-[#4896FE] h-12 rounded"></div>
              <div class="bg-[#887CFD] h-14 rounded"></div>
              <div class="bg-[#5347CE] h-12 rounded"></div>
            </div>
            <p class="text-xs mt-1">$1,765.09</p>
            <p class="text-xs text-gray-500">Nov</p>
          </div>

          <!-- Dec -->
          <div class="flex flex-col items-center">
            <div class="flex flex-col justify-end gap-1 w-10 sm:w-20 h-34">
              <div class="bg-[#16C8C7] h-6 rounded"></div>
              <div class="bg-[#23bdbd] h-9 rounded"></div>
              <div class="bg-[#4896FE] h-12 rounded"></div>
              <div class="bg-[#887CFD] h-15 rounded"></div>
              <div class="bg-[#5347CE] h-18 rounded"></div>
            </div>
            <p class="text-xs mt-1">$4,005.65</p>
            <p class="text-xs text-gray-500">Dec</p>
          </div>
        </div>

        <!-- Legend -->
        <div
          class="flex justify-center gap-4 mt-4 flex-wrap text-xs text-gray-600"
        >
          <span class="flex items-center"
            ><span class="w-3 h-3 bg-blue-900 rounded mr-1"></span>China</span
          >
          <span class="flex items-center"
            ><span class="w-3 h-3 bg-blue-700 rounded mr-1"></span>UE</span
          >
          <span class="flex items-center"
            ><span class="w-3 h-3 bg-blue-500 rounded mr-1"></span>USA</span
          >
          <span class="flex items-center"
            ><span class="w-3 h-3 bg-blue-300 rounded mr-1"></span>Canada</span
          >
          <span class="flex items-center"
            ><span class="w-3 h-3 bg-teal-300 rounded mr-1"></span>Other</span
          >
        </div>
      </div>

      <!-- Total Subscriber -->
      <div class="bg-white rounded-xl shadow p-6 w-full lg:w-1/3">
        <div class="flex flex-col sm:flex-row gap-2 justify-between items-center mb-4">
          <div class="flex items-center gap-1">
            <img
              src="../assets/Icons/ic--outline-people.svg"
              alt=""
              class="w-4 h-4"
            />
            <h3 class="font-semibold">Total Subscriber</h3>
          </div>
          <div
            class="flex items-center px-1 bg-[#f3f9f9] border-gray-300 rounded"
          >
            <button class="text-gray-400 py-1 text-sm cursor-pointer">
              Weekly
            </button>
            <img
              src="../assets/Icons/iconamoon--arrow-up-2-thin.svg"
              alt=""
              class="w-4 h-4"
            />
          </div>
        </div>
        <p class="text-2xl font-semibold">24,473</p>
        <div class="flex gap-2 items-center pt-2">
          <div
            class="flex items-center border border-[#dff8f8] bg-[#dff8f8] px-1 rounded"
          >
            <p class="text-[#96e8e8]">8.3%</p>
            <img
              src="../assets/Icons/guidance--up-right-arrow.svg"
              alt=""
              class="w-4 h-3"
            />
          </div>
          <p class="text-gray-400">+745 <span class="text-sm">Increased</span></p>
        </div>

        <!-- Bar chart -->
        <div class="flex justify-between items-end h-32 mt-6">
          <div class="flex flex-col items-center">
            <div class="bg-gray-300 w-6 h-6 rounded"></div>
            <p class="text-xs mt-1">Sun</p>
          </div>
          <div class="flex flex-col items-center">
            <div class="bg-gray-300 w-6 h-12 rounded"></div>
            <p class="text-xs mt-1">Mon</p>
          </div>
          <div class="flex flex-col items-center">
            <div
              class="bg-gradient-to-t from-blue-400 to-purple-500 w-6 h-32 rounded"
            ></div>
            <p class="text-xs mt-1">Tue</p>
          </div>
          <div class="flex flex-col items-center">
            <div class="bg-gray-300 w-6 h-12 rounded"></div>
            <p class="text-xs mt-1">Wed</p>
          </div>
          <div class="flex flex-col items-center">
            <div class="bg-gray-300 w-6 h-16 rounded"></div>
            <p class="text-xs mt-1">Thu</p>
          </div>
          <div class="flex flex-col items-center">
            <div class="bg-gray-300 w-6 h-20 rounded"></div>
            <p class="text-xs mt-1">Fri</p>
          </div>
          <div class="flex flex-col items-center">
            <div class="bg-gray-300 w-6 h-24 rounded"></div>
            <p class="text-xs mt-1">Sat</p>
          </div>
        </div>
      </div>
    </section>
    <div class="p-6 bg-gray-50 min-h-screen">
      <div class="grid grid-cols-1 lg:grid-cols-2 gap-6">
        <!-- Sales Distribution Card -->
        <div class="bg-white rounded-2xl shadow p-4">
          <div class="flex justify-between items-center mb-4">
            <div class="flex items-center gap-2">
              <img
                src="../assets/Icons/hugeicons--distribution.svg"
                alt=""
                class="w-4 h-4"
              />
              <h2 class="text-sm font-medium">Sales Distribution</h2>
            </div>
            <div class="flex items-center gap-1 px-2 bg-[#f3f9f9]">
              <p class="cursor-pointer text-sm">Monthly</p>
              <img
                src="../assets/Icons/oui--arrow-down.svg"
                alt=""
                class="w-4 h-4"
              />
            </div>
          </div>
          <div class="flex flex-col items-center justify-center space-x-4">
            <div
              class="flex justify-between lg:gap-8 xl:justify-between text-sm"
            >
              <div class="flex items-center space-x-2">
                <span class="w-3 h-3 rounded-full bg-[#38cfd9]"></span>
                <div class="flex flex-col items-center xl:text-sm">
                  Website:
                  <span class="font-semibold text-gray-800 xl:text-lg"
                    >$374.82</span
                  >
                </div>
              </div>
              <div class="flex items-center space-x-2">
                <span class="w-3 h-3 rounded-full bg-[#3fa9f5]"></span>
                <div class="flex flex-col items-center xl:text-sm">
                  Mobile App:
                  <span class="font-semibold text-gray-800 xl:text-lg"
                    >$241.60</span
                  >
                </div>
              </div>
              <div class="flex items-center space-x-2">
                <span class="w-3 h-3 rounded-full bg-[#7c5ce1]"></span>
                <div class="flex flex-col items-center xl:text-sm">
                  Other:
                  <span class="font-semibold text-gray-800 xl:text-lg"
                    >$213.42</span
                  >
                </div>
              </div>
            </div>
            <div class="w-60 h-60">
              <canvas ref="donutChart" class="w-full h-full"></canvas>
            </div>
          </div>
        </div>

        <!-- List of Integration Card -->
        <div class="bg-white rounded-2xl shadow p-4">
          <div class="flex justify-between items-center mb-4">
            <div class="flex items-center gap-2">
              <img
                src="../assets/Icons/fluent--arrow-swap-16-regular.svg"
                alt=""
              />
              <h2 class="text-sm font-medium">List of Integration</h2>
            </div>
            <a href="#" class="text-sm text-blue-500">See All</a>
          </div>
          <table
            class="w-full text-sm text-left min-w-full border-separate border-spacing-y-2"
          >
            <thead
              class="text-gray-400 bg-gray-100 hidden sm:table-header-group"
            >
              <tr class="px-4 py-3">
                <th></th>
                <th class="px-4 py-2">Application</th>
                <th class="px-4 py-2">Type</th>
                <th class="px-4 py-2">Rate</th>
                <th class="px-4 py-2">Profit</th>
              </tr>
            </thead>
            <tbody class="text-gray-700">
              <tr
                v-for="item in integrations"
                :key="item.name"
                class="border-t border-gray-200 flex flex-col sm:table-row"
              >
                <td class="pt-4 sm:pt-2 sm:pb-2 block sm:table-cell">
                  <input type="checkbox" />
                </td>
                <td class="px-4 py-2 block sm:table-cell">
                  <span class="block font-semibold text-gray-400 sm:hidden"
                    >Application</span
                  >
                  <div class="flex items-center space-x-2 py-2">
                    <img :src="item.icon" class="w-5 h-5" />
                    <span class="font-medium">{{ item.name }}</span>
                  </div>
                </td>
                <td class="px-4 py-2 block sm:table-cell">
                  <span class="block font-semibold text-gray-400 sm:hidden"
                    >Type</span
                  >
                  {{ item.type }}
                </td>
                <td class="w-24 px-4 py-2 block sm:table-cell">
                  <span class="block font-semibold text-gray-400 sm:hidden"
                    >Rate</span
                  >
                  <div class="bg-gray-200 rounded-full h-2">
                    <div
                      class="bg-blue-500 h-2 rounded-full"
                      :style="{ width: item.rate + '%' }"
                    ></div>
                  </div>
                </td>
                <td class="font-semibold px-4 py-3 block sm:table-cell">
                  <span class="block font-semibold text-gray-400 sm:hidden"
                    >Profit</span
                  >
                  ${{ item.profit }}
                </td>
              </tr>
            </tbody>
          </table>
        </div>
      </div>
    </div>
  </div>
</template>
<style scoped>
</style>