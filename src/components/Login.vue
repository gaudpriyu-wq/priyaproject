<template>
  <div class="min-h-screen flex items-center justify-center bg-gray-100">   
    <div class="bg-white p-8 rounded-2xl shadow-lg w-full max-w-md"> 
      <h2 class="text-2xl font-bold text-center mb-6 text-blue-600">
        Login to Your Account
      </h2>
      <form class="space-y-4 mt-" @submit.prevent="handleLogin">
        <!-- Email -->
        <div class="mb-4 text-left mt-8">
          <label class="block text-sm font-medium text-gray-600 mb-1">
            Email
          </label>
          <input
            type="email"
            v-model="email"
            placeholder="Enter email"
            class="w-full px-4 py-2 border rounded-lg focus:outline-none focus:ring-2 focus:ring-blue-400"
          />
        </div>

        <!-- Password -->
        <div class="mb-6 text-left mt-8">
          <label class="block text-sm font-medium text-gray-600 mb-1">
            Password
          </label>
          <input
            type="password"
            v-model="password"
            placeholder="Enter password"
            class="w-full px-4 py-2 border rounded-lg focus:outline-none focus:ring-2 focus:ring-blue-400"
          />
        </div>

        <!-- Button -->
        <button
          type="submit"
          class="mt-8 w-full bg-blue-500 text-white py-2 rounded-lg hover:bg-blue-600 transition duration-200"
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
      password: ""
    };
  },
  methods: {
    handleLogin() {
      if (!this.email || !this.password) {
        alert("Please fill all fields");
        return;
      }
      console.log("Login Data:", this.email, this.password);
    }
  }
};
</script>