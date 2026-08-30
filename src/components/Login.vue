<template>
  <div class="login-page d-flex align-items-center justify-content-center min-vh-100">
    <div class="login-card card shadow-lg p-5" style="width: 100%; max-width: 400px;">
      <div class="card-body">
        <h2 class="card-title text-center mb-4 text-primary">
          Login to Your Account
        </h2>
        <form @submit.prevent="handleLogin">
          <!-- Email Form Group -->
          <div class="mb-3 row align-items-center">
            <label for="emailInput" class="col-4 col-form-label">Email</label>
            <div class="col-8">
              <input
                type="email"
                v-model="email"
                class="form-control"
                id="emailInput"
                placeholder="Enter your email"
                required
              />
             
            </div>
          </div>

          <!-- Password Form Group -->
          <div class="mb-4 row align-items-center">
            <label for="passwordInput" class="col-4 col-form-label">Password</label>
            <div class="col-8">
              <input
                type="password"
                v-model="password"
                class="form-control"
                id="passwordInput"
                placeholder="Enter your password"
                required
              />
            </div>
          </div>

          <!-- Remember Me Checkbox -->
          <div class="mb-3 form-check">
            <input
              type="checkbox"
              class="form-check-input"
              id="rememberCheck"
            />
            <label class="form-check-label" for="rememberCheck">
              Remember me
            </label>
          </div>

          <!-- Submit Button -->
          <button
            type="submit"
            class="btn btn-success w-100 btn-lg mb-3"
          >
            Login
          </button>

          <!-- Additional Links -->
          <div class="text-center">
            <small>
              <a href="#" class="text-decoration-none">Forgot Password?</a> |
              <a href="#" class="text-decoration-none">Sign Up</a>
            </small>
          </div>
        </form>
      </div>
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
        alert("Please fill all fields");
        this.istrue = true;
        return;
      }
      console.log("Login Data:", this.email, this.password);
      console.log("after if", this.istrue);
      
      // Store user email in session
      sessionStorage.setItem("userEmail", this.email);
      
      // Navigate to dashboard
      this.$router.push("/dashboard");
    }
  }
};
</script>

<style scoped>
.login-page {
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  min-height: 100vh;
}

.login-card {
  border: none;
  border-radius: 0.5rem;
  backdrop-filter: blur(10px);
  animation: slideIn 0.5s ease-out;
}

@keyframes slideIn {
  from {
    opacity: 0;
    transform: translateY(20px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.card-body {
  padding: 2rem;
}

.form-control {
  border-radius: 0.375rem;
  border: 1px solid #dee2e6;
  transition: all 0.3s ease;
}

.form-control:focus {
  border-color: #667eea;
  box-shadow: 0 0 0 0.2rem rgba(102, 126, 234, 0.25);
}

.btn-primary {
  background-color: #667eea;
  border-color: #667eea;
  font-weight: 600;
  letter-spacing: 0.5px;
  transition: all 0.3s ease;
}

.btn-primary:hover {
  background-color: #5568d3;
  border-color: #5568d3;
  transform: translateY(-2px);
  box-shadow: 0 10px 20px rgba(102, 126, 234, 0.3);
}

.card-title {
  font-weight: 700;
  letter-spacing: 0.5px;
}

.form-check-input:checked {
  background-color: #667eea;
  border-color: #667eea;
}

a {
  color: #667eea;
  transition: color 0.3s ease;
}

a:hover {
  color: #5568d3;
}

.min-vh-100 {
  min-height: 100vh;
}
</style>