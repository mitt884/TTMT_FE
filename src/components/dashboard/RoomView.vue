<template>
  <div class="room-view">
    <h1 class="title">Xem phòng máy</h1>

    <!-- Stats Grid -->
    <div class="stats-grid">
      <div class="stat-card">
        <div class="stat-number">24</div>
        <div class="stat-label">Máy tính hoạt động</div>
        <div class="stat-icon">🖥️</div>
      </div>
      <div class="stat-card">
        <div class="stat-number">2</div>
        <div class="stat-label">Máy bảo trì</div>
        <div class="stat-icon">🔧</div>
      </div>
      <div class="stat-card">
        <div class="stat-number">98%</div>
        <div class="stat-label">Tỷ lệ hoạt động</div>
        <div class="stat-icon">📊</div>
      </div>
      <div class="stat-card">
        <div class="stat-number">15</div>
        <div class="stat-label">Người dùng online</div>
        <div class="stat-icon">👥</div>
      </div>
    </div>

    <!-- Content Section -->
    <div class="content-section">
      <div class="section-header">
        <h2>Chi tiết phòng máy</h2>
        <button class="refresh-btn">🔄 Làm mới</button>
      </div>

      <!-- Room Layout -->
      <div class="room-layout">
        <div class="room-grid">
          <!-- Dãy A -->
          <div class="row-section">
            <div class="row-label">Dãy A</div>
            <div class="computer-grid">
              <div class="computer-row">
                <div class="computer available">A1</div>
                <div class="computer available">A2</div>
                <div class="computer available">A3</div>
                <div class="computer available">A4</div>
                <div class="computer available">A5</div>
                <div class="computer available">A6</div>
              </div>
              <div class="computer-row">
                <div class="computer available">A7</div>
                <div class="computer available">A8</div>
                <div class="computer available">A9</div>
                <div class="computer available">A10</div>
                <div class="computer available">A11</div>
                <div class="computer available">A12</div>
              </div>
              <div class="computer-row">
                <div class="computer available">A13</div>
                <div class="computer available">A14</div>
                <div class="computer available">A15</div>
                <div class="computer available">A16</div>
                <div class="computer available">A17</div>
                <div class="computer available">A18</div>
              </div>
              <div class="computer-row">
                <div class="computer available">A19</div>
                <div class="computer available">A20</div>
                <div class="computer available">A21</div>
                <div class="computer available">A22</div>
                <div class="computer available">A23</div>
                <div class="computer available">A24</div>
              </div>
            </div>
          </div>

          <!-- Lối đi giữa -->
          <div class="aisle"></div>

          <!-- Dãy B -->
          <div class="row-section">
            <div class="row-label">Dãy B</div>
            <div class="computer-grid">
              <div class="computer-row">
                <div class="computer busy">B1</div>
                <div class="computer busy">B2</div>
                <div class="computer busy">B3</div>
                <div class="computer busy">B4</div>
                <div class="computer busy">B5</div>
                <div class="computer busy">B6</div>
              </div>
              <div class="computer-row">
                <div class="computer busy">B7</div>
                <div class="computer busy">B8</div>
                <div class="computer busy">B9</div>
                <div class="computer busy">B10</div>
                <div class="computer busy">B11</div>
                <div class="computer busy">B12</div>
              </div>
              <div class="computer-row">
                <div class="computer maintenance">B13</div>
                <div class="computer maintenance">B14</div>
                <div class="computer available">B15</div>
                <div class="computer available">B16</div>
                <div class="computer available">B17</div>
                <div class="computer available">B18</div>
              </div>
              <div class="computer-row">
                <div class="computer available">B19</div>
                <div class="computer available">B20</div>
                <div class="computer available">B21</div>
                <div class="computer available">B22</div>
                <div class="computer available">B23</div>
                <div class="computer available">B24</div>
              </div>
            </div>
          </div>
        </div>

        <!-- Chú thích -->
        <div class="legend">
          <div class="legend-item">
            <div class="legend-color available"></div>
            <span>Máy trống</span>
          </div>
          <div class="legend-item">
            <div class="legend-color busy"></div>
            <span>Máy đang sử dụng</span>
          </div>
          <div class="legend-item">
            <div class="legend-color maintenance"></div>
            <span>Máy bảo trì</span>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
</script>

<style scoped>
.room-view {
  flex: 1;
  width: 100vw;
  max-width: 100vw;
  background: #fff;
  padding: 32px;
  border-radius: 12px;
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.1);
  border: 1px solid #e0e0e0;
  min-height: 600px;
  animation: fadeIn 0.5s ease-out;
  box-sizing: border-box;
}

.title {
  font-size: 28px;
  font-weight: 700;
  margin-bottom: 32px;
  color: #000;
  border-bottom: 3px solid #000;
  padding-bottom: 12px;
  display: inline-block;
}

.stats-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
  gap: 20px;
  margin-bottom: 40px;
  width: 100vw;
  max-width: 100vw;
  box-sizing: border-box;
}

.stat-card {
  background: #000;
  color: #fff;
  padding: 24px;
  border-radius: 12px;
  border: 2px solid #333;
  transition: all 0.3s ease;
  position: relative;
  overflow: hidden;
}

.stat-card::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  width: 100vw;
  height: 4px;
  background: #fff;
  transform: scaleX(0);
  transition: transform 0.3s ease;
}

.stat-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 8px 25px rgba(0, 0, 0, 0.2);
  border-color: #555;
}

.stat-card:hover::before {
  transform: scaleX(1);
}

.stat-number {
  font-size: 36px;
  font-weight: 700;
  color: #fff;
  margin-bottom: 8px;
}

.stat-label {
  font-size: 14px;
  color: #ccc;
  font-weight: 500;
  margin-bottom: 12px;
}

.stat-icon {
  font-size: 24px;
  position: absolute;
  top: 24px;
  right: 24px;
  opacity: 0.6;
}

.content-section {
  background: #f8f9fa;
  padding: 24px;
  border-radius: 12px;
  border: 1px solid #e0e0e0;
}

.section-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 24px;
  padding-bottom: 16px;
  border-bottom: 2px solid #e0e0e0;
}

.section-header h2 {
  font-size: 20px;
  font-weight: 600;
  color: #000;
}

.refresh-btn {
  background: #000;
  color: #fff;
  border: none;
  padding: 10px 16px;
  border-radius: 8px;
  cursor: pointer;
  font-size: 14px;
  font-weight: 500;
  transition: all 0.3s ease;
}

.refresh-btn:hover {
  background: #333;
  transform: translateY(-2px);
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.2);
}

/* Room Layout Styles - Vertical Arrangement */
.room-layout {
  padding: 20px;
}

.room-grid {
  display: flex;
  flex-direction: row;
  justify-content: center;
  gap: 60px;
  margin-bottom: 30px;
}

.row-section {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 20px;
}

.row-label {
  font-size: 18px;
  font-weight: 600;
  color: #000;
  padding: 10px 20px;
  background: #f0f0f0;
  border-radius: 8px;
  text-align: center;
}

.computer-grid {
  display: grid;
  grid-template-rows: repeat(4, 1fr);
  gap: 12px;
}

.computer-row {
  display: grid;
  grid-template-columns: repeat(6, 1fr);
  gap: 12px;
}

.computer {
  width: 60px;
  height: 60px;
  border-radius: 8px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 12px;
  font-weight: 600;
  color: white;
  cursor: pointer;
  transition: all 0.3s ease;
  border: 2px solid transparent;
}

.computer.available {
  background: #28a745;
  border-color: #1e7e34;
}

.computer.busy {
  background: #6f42c1;
  border-color: #5a2d91;
}

.computer.maintenance {
  background: #dc3545;
  border-color: #c82333;
}

.computer:hover {
  transform: scale(1.1);
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.2);
}

.aisle {
  width: 4px;
  height: 100%;
  background: linear-gradient(180deg, #e0e0e0 0%, #f0f0f0 50%, #e0e0e0 100%);
  border-radius: 2px;
  align-self: stretch;
}

.legend {
  display: flex;
  justify-content: center;
  gap: 30px;
  margin-top: 20px;
  padding: 20px;
  background: #f8f9fa;
  border-radius: 8px;
  border: 1px solid #e0e0e0;
}

.legend-item {
  display: flex;
  align-items: center;
  gap: 8px;
}

.legend-color {
  width: 20px;
  height: 20px;
  border-radius: 4px;
  border: 2px solid transparent;
}

.legend-color.available {
  background: #28a745;
  border-color: #1e7e34;
}

.legend-color.busy {
  background: #6f42c1;
  border-color: #5a2d91;
}

.legend-color.maintenance {
  background: #dc3545;
  border-color: #c82333;
}

.legend-item span {
  font-size: 14px;
  color: #333;
  font-weight: 500;
}

@media (max-width: 768px) {
  .room-view {
    padding: 20px;
  }

  .title {
    font-size: 24px;
    margin-bottom: 24px;
  }

  .stats-grid {
    grid-template-columns: 1fr;
    gap: 16px;
    margin-bottom: 24px;
  }

  .content-section {
    padding: 20px;
  }

  .section-header {
    flex-direction: column;
    gap: 16px;
    align-items: flex-start;
  }

  .room-grid {
    flex-direction: column;
    gap: 40px;
  }

  .aisle {
    width: 100%;
    height: 4px;
    background: linear-gradient(90deg, #e0e0e0 0%, #f0f0f0 50%, #e0e0e0 100%);
  }

  .computer-row {
    grid-template-columns: repeat(3, 1fr);
  }

  .computer {
    width: 50px;
    height: 50px;
    font-size: 10px;
  }

  .legend {
    flex-direction: column;
    gap: 15px;
  }
}

@keyframes fadeIn {
  from {
    opacity: 0;
    transform: translateY(20px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}
</style>