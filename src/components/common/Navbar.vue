<template>
  <div class="navbar">
    <div class="logo">TTMT</div>
    <div class="role">
      <span class="role-name">Cán bộ TTMT</span>
    </div>
  </div>
</template>

<script setup>
</script>

<style scoped>
.navbar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  background: #000;
  color: #fff;
  padding: 16px 24px;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.3);
  border-bottom: 1px solid #333;
  position: relative;
  z-index: 1000;
}

.logo {
  font-size: 24px;
  font-weight: 700;
  color: #fff;
  letter-spacing: 1px;
  transition: color 0.3s ease;
}

.logo:hover {
  color: #f0f0f0;
}

.role {
  display: flex;
  align-items: center;
  gap: 12px;
  background: #1a1a1a;
  padding: 8px 16px;
  border-radius: 25px;
  border: 1px solid #333;
  transition: all 0.3s ease;
}

.role:hover {
  background: #2a2a2a;
  border-color: #555;
  transform: translateY(-2px);
}

.role-circle:hover {
  background: #f0f0f0;
  transform: scale(1.05);
}

.role-name {
  font-size: 14px;
  font-weight: 500;
  color: #e0e0e0;
}

/* Responsive */
@media (max-width: 100%) {
  .navbar {
    padding: 12px 16px;
  }
  
  .logo {
    font-size: 20px;
  }
  
  .role {
    padding: 6px 12px;
  }
  
  
  .role-name {
    font-size: 12px;
  }
}
</style>