<script setup>
import DashboardSection from "./components/DashboardSection.vue";
import SidebarSection from "./components/SidebarSection.vue";
import SidebarView from "./components/SidebarView.vue"
import {ref} from "vue";
const showIcon = ref(true);
const  showSidebar = ref(false)
function toggleSidebar (){
  
  showSidebar.value = !showSidebar.value;
}
</script>

<template>
  <div class="flex flex-row items-start justify-center gap-2 md:gap-1 w-full max-w-[1440px] mx-auto h-screen">
    
        <sidebar-view  v-if="showSidebar" :toggle-sidebar="toggleSidebar"/>
    <sidebar-section class="w-1/5 hidden md:block"/>
    <dashboard-section class="w-full md:w-4/5"   :toggle-sidebar="toggleSidebar"/>
    </div>
</template>

<style scoped>

</style>
