<template>
  <div class="dashboard">
    <Navbar />

    <div class="main">
      <Sidebar
        :active-menu="activeMenu"
        @menu-click="activeMenu = $event"
      />

      <div class="content">
        <RoomView v-if="activeMenu === 'roomView'" />
        <!-- Các component khác -->
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";
import Navbar from "../components/common/Navbar.vue";
import Sidebar from "../components/common/Sidebar.vue";
import RoomView from "../components/dashboard/RoomView.vue";

const activeMenu = ref("roomView");
</script>

<style scoped>
.dashboard {
  height: 100vh;
  width: 100vw;
  display: flex;
  flex-direction: column;
  overflow: hidden;
}

.main {
  flex: 1;
  display: flex;
  width: 100vw;
  height: 100vh;
  overflow: hidden;
}

.content {
  flex: 1;
  background: #f5f5f5;
  padding: 20px;
  overflow-y: auto;
  overflow-x: hidden; 
  box-sizing: border-box;
  width: 100vw;       
  max-width: 100vw; 
}

</style>
