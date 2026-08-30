<template>
  <div class="dashboard-page min-h-screen bg-gradient-to-br from-slate-900 via-purple-900 to-slate-900">
    <!-- Header -->
    <header class="bg-gradient-to-r from-purple-600 to-blue-600 shadow-2xl sticky top-0 z-50">
      <div class="max-w-7xl mx-auto px-6 py-6 flex justify-between items-center">
        <div class="flex items-center gap-3">
          
          <h1 class="text-4xl font-bold text-white">Dashboard</h1>
        </div>
        <button
          @click="handleLogout"
          class="px-8 py-3 bg-amber-500 hover:bg-amber-600 text-white font-semibold rounded-lg transition duration-300 transform hover:scale-105 shadow-lg"
        >
          Logout
        </button>
      </div>
    </header>

    <!-- Main Content -->
    <main class="max-w-7xl mx-auto px-6 py-12">
      <!-- Welcome Section -->
      <section class="bg-gradient-to-r from-purple-500 to-pink-500 rounded-2xl shadow-2xl p-10 mb-12 text-white transform hover:scale-102 transition duration-300">
        <h2 class="text-4xl font-bold mb-3">Welcome Back! 👋</h2>
        <p class="text-lg font-semibold opacity-90">{{ userEmail }}</p>
        <p class="text-sm opacity-75 mt-2">You have 3 new notifications</p>
      </section>

      <!-- Stats Section -->
      <section class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-6 mb-12">
        <!-- Card 1: Total Users -->
        <div class="bg-gradient-to-br from-blue-500 to-blue-600 rounded-2xl shadow-2xl p-8 text-white transform hover:scale-105 transition duration-300 cursor-pointer group">
          <div class="flex items-center justify-between mb-6">
            <div>
              <p class="text-blue-100 text-sm font-semibold mb-1">Total Users</p>
              <div class="text-5xl font-bold group-hover:text-blue-200 transition">1.2K</div>
            </div>
            <div class="text-6xl opacity-20 group-hover:opacity-40 transition">👥</div>
          </div>
          <div class="flex items-center text-blue-100 text-sm">
            <span class="text-green-300 font-bold mr-2">↑ 12%</span>
            <span>from last week</span>
          </div>
        </div>

        <!-- Card 2: Revenue -->
        <div class="bg-gradient-to-br from-green-500 to-emerald-600 rounded-2xl shadow-2xl p-8 text-white transform hover:scale-105 transition duration-300 cursor-pointer group">
          <div class="flex items-center justify-between mb-6">
            <div>
              <p class="text-green-100 text-sm font-semibold mb-1">Revenue</p>
              <div class="text-5xl font-bold group-hover:text-green-200 transition">$45K</div>
            </div>
            <div class="text-6xl opacity-20 group-hover:opacity-40 transition">💰</div>
          </div>
          <div class="flex items-center text-green-100 text-sm">
            <span class="text-green-300 font-bold mr-2">↑ 8.3%</span>
            <span>from last week</span>
          </div>
        </div>

        <!-- Card 3: Active Sessions -->
        <div class="bg-gradient-to-br from-purple-500 to-indigo-600 rounded-2xl shadow-2xl p-8 text-white transform hover:scale-105 transition duration-300 cursor-pointer group">
          <div class="flex items-center justify-between mb-6">
            <div>
              <p class="text-purple-100 text-sm font-semibold mb-1">Active Sessions</p>
              <div class="text-5xl font-bold group-hover:text-purple-200 transition">324</div>
            </div>
            <div class="text-6xl opacity-20 group-hover:opacity-40 transition">🔗</div>
          </div>
          <div class="flex items-center text-purple-100 text-sm">
            <span class="text-green-300 font-bold mr-2">↑ 5.2%</span>
            <span>from last week</span>
          </div>
        </div>

        <!-- Card 4: Conversion Rate -->
        <div class="bg-gradient-to-br from-orange-500 to-red-600 rounded-2xl shadow-2xl p-8 text-white transform hover:scale-105 transition duration-300 cursor-pointer group">
          <div class="flex items-center justify-between mb-6">
            <div>
              <p class="text-orange-100 text-sm font-semibold mb-1">Conversion Rate</p>
              <div class="text-5xl font-bold group-hover:text-orange-200 transition">8.2%</div>
            </div>
            <div class="text-6xl opacity-20 group-hover:opacity-40 transition">📈</div>
          </div>
          <div class="flex items-center text-orange-100 text-sm">
            <span class="text-green-300 font-bold mr-2">↑ 2.1%</span>
            <span>from last week</span>
          </div>
        </div>
      </section>

      <!-- Charts & Activity Section -->
      <div class="grid grid-cols-1 lg:grid-cols-3 gap-6 mb-12">
        <!-- Recent Activity -->
        <div class="lg:col-span-2 bg-white bg-opacity-10 backdrop-blur-md rounded-2xl shadow-2xl p-8 border border-white border-opacity-20">
          <h3 class="text-2xl font-bold text-white mb-8 flex items-center gap-2">
            📊 Recent Activity
          </h3>
          <ul class="space-y-4">
            <li class="flex items-center text-gray-100 pb-4 border-b border-white border-opacity-10 hover:bg-white hover:bg-opacity-5 px-4 py-2 rounded-lg transition cursor-pointer">
              <span class="inline-block w-4 h-4 bg-blue-400 rounded-full mr-4"></span>
              <span class="flex-1">New user signup from Google</span>
              <span class="text-gray-400 text-sm">2 min ago</span>
            </li>
            <li class="flex items-center text-gray-100 pb-4 border-b border-white border-opacity-10 hover:bg-white hover:bg-opacity-5 px-4 py-2 rounded-lg transition cursor-pointer">
              <span class="inline-block w-4 h-4 bg-green-400 rounded-full mr-4"></span>
              <span class="flex-1">Payment received - Order #2341</span>
              <span class="text-gray-400 text-sm">5 min ago</span>
            </li>
            <li class="flex items-center text-gray-100 pb-4 border-b border-white border-opacity-10 hover:bg-white hover:bg-opacity-5 px-4 py-2 rounded-lg transition cursor-pointer">
              <span class="inline-block w-4 h-4 bg-purple-400 rounded-full mr-4"></span>
              <span class="flex-1">System update completed</span>
              <span class="text-gray-400 text-sm">1 hr ago</span>
            </li>
            <li class="flex items-center text-gray-100 pb-4 hover:bg-white hover:bg-opacity-5 px-4 py-2 rounded-lg transition cursor-pointer">
              <span class="inline-block w-4 h-4 bg-yellow-400 rounded-full mr-4"></span>
              <span class="flex-1">Database backup completed</span>
              <span class="text-gray-400 text-sm">3 hr ago</span>
            </li>
          </ul>
        </div>

        <!-- Quick Stats -->
        <div class="bg-white bg-opacity-10 backdrop-blur-md rounded-2xl shadow-2xl p-8 border border-white border-opacity-20">
          <h3 class="text-2xl font-bold text-white mb-8 flex items-center gap-2">
            ⚡ Quick Stats
          </h3>
          <div class="space-y-6">
            <div>
              <div class="flex justify-between mb-2">
                <span class="text-gray-100 font-semibold">Server Health</span>
                <span class="text-green-400 font-bold">98%</span>
              </div>
              <div class="w-full bg-gray-700 rounded-full h-2">
                <div class="bg-gradient-to-r from-green-400 to-emerald-500 h-2 rounded-full" style="width: 98%"></div>
              </div>
            </div>
            <div>
              <div class="flex justify-between mb-2">
                <span class="text-gray-100 font-semibold">CPU Usage</span>
                <span class="text-blue-400 font-bold">42%</span>
              </div>
              <div class="w-full bg-gray-700 rounded-full h-2">
                <div class="bg-gradient-to-r from-blue-400 to-cyan-500 h-2 rounded-full" style="width: 42%"></div>
              </div>
            </div>
            <div>
              <div class="flex justify-between mb-2">
                <span class="text-gray-100 font-semibold">Storage</span>
                <span class="text-orange-400 font-bold">65%</span>
              </div>
              <div class="w-full bg-gray-700 rounded-full h-2">
                <div class="bg-gradient-to-r from-orange-400 to-red-500 h-2 rounded-full" style="width: 65%"></div>
              </div>
            </div>
          </div>
        </div>
      </div>

      <!-- Bottom Stats -->
      <section class="grid grid-cols-1 md:grid-cols-2 gap-6">
        <!-- Top Performing -->
        <div class="bg-white bg-opacity-10 backdrop-blur-md rounded-2xl shadow-2xl p-8 border border-white border-opacity-20">
          <h3 class="text-2xl font-bold text-white mb-6 flex items-center gap-2">
            🏆 Top Performing
          </h3>
          <div class="space-y-3">
            <div class="flex justify-between items-center hover:bg-white hover:bg-opacity-5 px-4 py-3 rounded-lg transition cursor-pointer">
              <span class="text-gray-100 font-semibold">Product A</span>
              <span class="text-green-400 font-bold">$12.5K</span>
            </div>
            <div class="flex justify-between items-center hover:bg-white hover:bg-opacity-5 px-4 py-3 rounded-lg transition cursor-pointer">
              <span class="text-gray-100 font-semibold">Product B</span>
              <span class="text-green-400 font-bold">$8.3K</span>
            </div>
            <div class="flex justify-between items-center hover:bg-white hover:bg-opacity-5 px-4 py-3 rounded-lg transition cursor-pointer">
              <span class="text-gray-100 font-semibold">Product C</span>
              <span class="text-green-400 font-bold">$6.2K</span>
            </div>
          </div>
        </div>
      </section>
    </main>
  </div>
</template>

<script>
export default {
  name: "DashboardPage",
  data() {
    return {
      userEmail: ""
    };
  },
  mounted() {
    // Get user email from sessionStorage or localStorage
    this.userEmail = sessionStorage.getItem("userEmail") || "User";
  },
  methods: {
    handleLogout() {
      // Clear user data
      sessionStorage.removeItem("userEmail");
      // Redirect to login
      this.$router.push("/");
    }
  }
};
</script>

<style scoped>
* {
  transition: all 0.3s ease;
}

.dashboard-page {
  min-height: 100vh;
  background: linear-gradient(135deg, #1e1b4b 0%, #2d1b4e 50%, #1e1b4b 100%);
  animation: backgroundShift 15s ease-in-out infinite;
}

@keyframes backgroundShift {
  0%, 100% {
    background: linear-gradient(135deg, #1e1b4b 0%, #2d1b4e 50%, #1e1b4b 100%);
  }
  50% {
    background: linear-gradient(135deg, #2d1b4e 0%, #1e1b4b 50%, #2d1b4e 100%);
  }
}

/* Header Styles */
header {
  backdrop-filter: blur(10px);
  border-bottom: 1px solid rgba(255, 255, 255, 0.1);
  animation: slideDown 0.5s ease-out;
}

@keyframes slideDown {
  from {
    transform: translateY(-100%);
    opacity: 0;
  }
  to {
    transform: translateY(0);
    opacity: 1;
  }
}

h1 {
  font-size: 2.5rem;
  background: linear-gradient(135deg, #a78bfa 0%, #60a5fa 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

button:hover {
  transform: translateY(-2px);
  box-shadow: 0 10px 20px rgba(239, 68, 68, 0.4);
}

button:active {
  transform: translateY(0);
}

/* Welcome Section */
section:first-of-type {
  background: linear-gradient(135deg, rgba(168, 85, 247, 0.8) 0%, rgba(236, 72, 153, 0.8) 100%);
  backdrop-filter: blur(10px);
  border: 1px solid rgba(255, 255, 255, 0.2);
  animation: fadeInUp 0.6s ease-out 0.1s backwards;
  cursor: pointer;
  position: relative;
  overflow: hidden;
}

section:first-of-type::before {
  content: '';
  position: absolute;
  top: -50%;
  right: -50%;
  width: 100%;
  height: 100%;
  background: linear-gradient(45deg, transparent, rgba(255, 255, 255, 0.1), transparent);
  transform: rotate(45deg);
  animation: shine 3s infinite;
}

@keyframes shine {
  0% {
    transform: translateX(-100%) translateY(-100%) rotate(45deg);
  }
  100% {
    transform: translateX(100%) translateY(100%) rotate(45deg);
  }
}

section:first-of-type:hover {
  transform: translateY(-5px);
  box-shadow: 0 20px 40px rgba(168, 85, 247, 0.4);
}

/* Stats Cards */
.grid.grid-cols-1.md\\:grid-cols-2.lg\\:grid-cols-4 > div {
  animation: fadeInUp 0.6s ease-out backwards;
  border: 1px solid rgba(255, 255, 255, 0.1);
  backdrop-filter: blur(10px);
  position: relative;
  overflow: hidden;
}

.grid.grid-cols-1.md\\:grid-cols-2.lg\\:grid-cols-4 > div:nth-child(1) {
  animation-delay: 0.2s;
}

.grid.grid-cols-1.md\\:grid-cols-2.lg\\:grid-cols-4 > div:nth-child(2) {
  animation-delay: 0.3s;
}

.grid.grid-cols-1.md\\:grid-cols-2.lg\\:grid-cols-4 > div:nth-child(3) {
  animation-delay: 0.4s;
}

.grid.grid-cols-1.md\\:grid-cols-2.lg\\:grid-cols-4 > div:nth-child(4) {
  animation-delay: 0.5s;
}

.grid.grid-cols-1.md\\:grid-cols-2.lg\\:grid-cols-4 > div::after {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: linear-gradient(135deg, rgba(255, 255, 255, 0.1) 0%, transparent 50%);
  opacity: 0;
  transition: opacity 0.3s;
}

.grid.grid-cols-1.md\\:grid-cols-2.lg\\:grid-cols-4 > div:hover::after {
  opacity: 1;
}

.group:hover {
  transform: translateY(-8px);
  box-shadow: 0 25px 50px rgba(0, 0, 0, 0.3);
}

/* Activity & Stats Sections */
.lg\\:col-span-2,
.bg-white.bg-opacity-10.backdrop-blur-md {
  background: linear-gradient(135deg, rgba(255, 255, 255, 0.05) 0%, rgba(255, 255, 255, 0.02) 100%);
  backdrop-filter: blur(20px);
  border: 1px solid rgba(255, 255, 255, 0.15);
  animation: fadeInUp 0.6s ease-out 0.3s backwards;
  border-radius: 1rem;
}

h3 {
  font-size: 1.5rem;
  background: linear-gradient(135deg, #a78bfa 0%, #60a5fa 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
  margin-bottom: 1.5rem;
}

/* List Items Animation */
li {
  animation: fadeInLeft 0.4s ease-out backwards;
}

li:nth-child(1) {
  animation-delay: 0.4s;
}

li:nth-child(2) {
  animation-delay: 0.5s;
}

li:nth-child(3) {
  animation-delay: 0.6s;
}

li:nth-child(4) {
  animation-delay: 0.7s;
}

li:hover {
  background: rgba(255, 255, 255, 0.08) !important;
  transform: translateX(5px);
}

/* Progress Bars */
.w-full.bg-gray-700 {
  background: rgba(55, 65, 81, 0.5) !important;
  border-radius: 9999px;
  overflow: hidden;
}

.w-full.bg-gray-700 > div {
  animation: widthIncrease 1s ease-out;
  border-radius: 9999px;
  box-shadow: 0 0 20px currentColor;
}

@keyframes widthIncrease {
  from {
    width: 0 !important;
  }
}

/* Animations */
@keyframes fadeInUp {
  from {
    opacity: 0;
    transform: translateY(20px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

@keyframes fadeInLeft {
  from {
    opacity: 0;
    transform: translateX(-20px);
  }
  to {
    opacity: 1;
    transform: translateX(0);
  }
}

/* Responsive */
@media (max-width: 768px) {
  h1 {
    font-size: 1.875rem;
  }

  h3 {
    font-size: 1.25rem;
  }

  section:first-of-type {
    padding: 1.5rem;
  }
}

/* Smooth Scrollbar */
::-webkit-scrollbar {
  width: 8px;
}

::-webkit-scrollbar-track {
  background: rgba(255, 255, 255, 0.05);
}

::-webkit-scrollbar-thumb {
  background: linear-gradient(135deg, #a78bfa 0%, #60a5fa 100%);
  border-radius: 10px;
}

::-webkit-scrollbar-thumb:hover {
  background: linear-gradient(135deg, #c084fc 0%, #93c5fd 100%);
}
</style>
