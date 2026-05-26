<template>
  <div class="login-page min-h-screen flex items-center justify-center">
    <div class="login-card bg-white p-8 rounded-2xl shadow-lg w-full max-w-md">
      <h2 class="text-2xl font-bold text-center mb-6 text-blue-600">
        Login to Your Account
      </h2>
      <form class="space-y-6" @submit.prevent="handleLogin">
        <!-- Email -->
        <div class="text-left">
          <label class="block text-sm font-medium text-gray-600 mb-2">
            Email
          </label>
          <input
            type="email"
            v-model="email"
            placeholder="Enter email"
            class="w-full px-4 py-3 border rounded-lg focus:outline-none focus:ring-2 focus:ring-blue-400"
          />
        </div>

        <!-- Password -->
        <div class="text-left">
          <label class="block text-sm font-medium text-gray-600 mb-2">
            Password
          </label>
          <input
            type="password"
            v-model="password"
            placeholder="Enter password"
            class="w-full px-4 py-3 border rounded-lg focus:outline-none focus:ring-2 focus:ring-blue-400"
          />
        </div>

        <!-- Button -->
        <button
          type="submit"
          class="login-button w-full bg-blue-600 text-white py-3 rounded-lg hover:bg-blue-700 transition duration-200"
        >
          Login
        </button>
      </form>
    </div>
  </div>
</template>

<script>
export default {
  name: "LoginPage",
  data() {
    return {
      email: "",
      password: "",
      istrue: false
    };
  },
  methods: {
    handleLogin() {
      if (!this.email || !this.password) {
        alert("Please fill all fields and add");
        this.istrue = true;
        return;
      }
      console.log("Login Data:", this.email, this.password);
      console.log("after if", this.istrue);
    }
  }
};
</script>

<style scoped>
.login-page {
  background: linear-gradient(180deg, #e0f2fe 0%, #f8fafc 100%);
}

.login-card {
  border: 1px solid rgba(59, 130, 246, 0.15);
  backdrop-filter: blur(8px);
}

.login-card input {
  border-color: #cbd5e1;
}

.login-card input:focus {
  border-color: #3b82f6;
}

.login-button {
  background-color: #2563eb;
  box-shadow: 0 10px 25px rgba(37, 99, 235, 0.18);
}

.login-button:hover {
  background-color: #1d4ed8;
}
</style>