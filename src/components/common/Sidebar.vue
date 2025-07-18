<template>
  <div class="sidebar">
    <h2 class="menu-title">Menu</h2>

    <button 
      class="menu-btn"
      :class="{ active: activeMenu === 'roomView' }"
      @click="$emit('menu-click', 'roomView')"
    >
      <span class="menu-icon">📊</span>
      Xem phòng máy
    </button>

    <button 
      class="menu-btn"
      :class="{ active: activeMenu === 'management' }"
      @click="$emit('menu-click', 'management')"
    >
      <span class="menu-icon">⚙️</span>
      Quản lý thiết bị
    </button>

    <button 
      class="menu-btn"
      :class="{ active: activeMenu === 'reports' }"
      @click="$emit('menu-click', 'reports')"
    >
      <span class="menu-icon">📈</span>
      Báo cáo
    </button>

    <button 
      class="menu-btn"
      :class="{ active: activeMenu === 'settings' }"
      @click="$emit('menu-click', 'settings')"
    >
      <span class="menu-icon">🔧</span>
      Cài đặt
    </button>
  </div>
</template>

<script setup>
defineProps({
  activeMenu: String
});
defineEmits(['menu-click']);
</script>

<style scoped>
.sidebar {
  width: 280px;
  height: 100%;
  background: #1a1a1a;
  color: #fff;
  padding: 24px;
  border-right: 1px solid #333;
  box-shadow: 2px 0 10px rgba(0, 0, 0, 0.3);
  overflow-y: auto;
}

.menu-title {
  font-size: 18px;
  font-weight: 600;
  margin-bottom: 24px;
  color: #fff;
  padding-bottom: 12px;
  border-bottom: 2px solid #333;
  text-transform: uppercase;
  letter-spacing: 1px;
}

.menu-btn {
  width: 100%;
  text-align: left;
  background: #2a2a2a;
  color: #e0e0e0;
  border: 1px solid #333;
  padding: 16px 20px;
  border-radius: 8px;
  cursor: pointer;
  transition: all 0.3s ease;
  font-size: 14px;
  font-weight: 500;
  margin-bottom: 8px;
  position: relative;
  overflow: hidden;
  display: flex;
  align-items: center;
  gap: 12px;
}

.menu-btn:hover {
  background: #333;
  color: #fff;
  border-color: #555;
  transform: translateY(-2px);
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.3);
}

.menu-btn.active {
  background: #fff;
  color: #000;
  border-color: #fff;
  box-shadow: 0 4px 12px rgba(255, 255, 255, 0.2);
}

.menu-btn.active:hover {
  background: #f0f0f0;
}

.menu-icon {
  font-size: 16px;
  opacity: 0.8;
}

.menu-btn.active .menu-icon {
  opacity: 1;
}

.sidebar::-webkit-scrollbar {
  width: 6px;
}

.sidebar::-webkit-scrollbar-track {
  background: #1a1a1a;
}

.sidebar::-webkit-scrollbar-thumb {
  background: #333;
  border-radius: 3px;
}

.sidebar::-webkit-scrollbar-thumb:hover {
  background: #555;
}
</style>
