<template>
  <div class="register-page d-flex align-items-center justify-content-center">
    <div class="register-card card shadow-lg">
      <div class="card-body">
        <p class="register-eyebrow text-center mb-2">GET STARTED</p>
        <h2 class="card-title text-center mb-2 text-primary">
          Create Your Account
        </h2>
        <p class="register-subtitle text-center mb-4">Create an account to continue</p>
        <form @submit.prevent="handleRegister">
          <!-- First Name Form Group -->
          <div class="mb-3 row align-items-center">
            <label for="firstNameInput" class="col-4 col-form-label">First Name</label>
            <div class="col-8">
              <input
                type="text"
                v-model="firstName"
                class="form-control"
                id="firstNameInput"
                placeholder="Enter your first name"
                required
              />
            </div>
          </div>

          <!-- Last Name Form Group -->
          <div class="mb-3 row align-items-center">
            <label for="lastNameInput" class="col-4 col-form-label">Last Name</label>
            <div class="col-8">
              <input
                type="text"
                v-model="lastName"
                class="form-control"
                id="lastNameInput"
                placeholder="Enter your last name"
                required
              />
            </div>
          </div>

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

          <!-- Phone Form Group -->
          <div class="mb-3 row align-items-center">
            <label for="phoneInput" class="col-4 col-form-label">Phone</label>
            <div class="col-8">
              <input
                type="tel"
                v-model="phone"
                class="form-control"
                id="phoneInput"
                placeholder="Enter your phone number"
                required
              />
            </div>
          </div>

          <!-- Password Form Group -->
          <div class="mb-3 row align-items-center">
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

          <!-- Confirm Password Form Group -->
          <div class="mb-4 row align-items-center">
            <label for="confirmPasswordInput" class="col-4 col-form-label">Confirm Password</label>
            <div class="col-8">
              <input
                type="password"
                v-model="confirmPassword"
                class="form-control"
                id="confirmPasswordInput"
                placeholder="Confirm your password"
                required
              />
            </div>
          </div>

          <!-- Terms & Conditions Checkbox -->
          <div class="mb-3 row align-items-center">
            <div class="col-4"></div>
            <div class="col-8">
              <div class="form-check">
                <input
                  type="checkbox"
                  class="form-check-input"
                  id="termsCheck"
                  v-model="acceptTerms"
                  required
                />
                <label class="form-check-label" for="termsCheck">
                  I agree to the terms and conditions
                </label>
              </div>
            </div>
          </div>

          <!-- Submit Button -->
          <button
            type="submit"
            class="btn btn-primary w-100 btn-lg mb-3"
          >
            Register
          </button>

          <!-- Login Link -->
          <div class="text-center">
            <small>
              Already have an account?
              <router-link to="/" class="text-decoration-none">Login here</router-link>
            </small>
          </div>
        </form>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "RegisterPage",
  data() {
    return {
      firstName: "",
      lastName: "",
      email: "",
      phone: "",
      password: "",
      confirmPassword: "",
      acceptTerms: false
    };
  },
  methods: {
    handleRegister() {
      if (!this.firstName || !this.lastName || !this.email || !this.phone || !this.password || !this.confirmPassword) {
        alert("Please fill all fields");
        return;
      }

      if (this.password !== this.confirmPassword) {
        alert("Passwords do not match");
        return;
      }

      if (!this.acceptTerms) {
        alert("Please accept the terms and conditions");
        return;
      }

      console.log("Registration Data:", {
        firstName: this.firstName,
        lastName: this.lastName,
        email: this.email,
        phone: this.phone
      });

      // Store user email in session
      sessionStorage.setItem("userEmail", this.email);

      // Navigate to dashboard
      this.$router.push("/dashboard");
    }
  }
};
</script>

<style scoped>
.register-page {
  min-height: 100vh;
  padding: 2rem 1rem;
  background: radial-gradient(circle at 15% 10%, #dce7ff 0, transparent 32%),
    linear-gradient(135deg, #f4f7ff 0%, #eef1fb 55%, #f8f5ff 100%);
}

.register-card {
  width: 100%;
  max-width: 520px;
  border: none;
  border-radius: 1.25rem;
  background: rgba(255, 255, 255, 0.96);
  box-shadow: 0 24px 70px rgba(54, 70, 120, 0.14) !important;
  animation: slideIn 0.45s ease-out;
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
  padding: 2.5rem;
}

.register-eyebrow {
  color: #667eea;
  font-size: 0.72rem;
  font-weight: 700;
  letter-spacing: 0.16em;
}

.register-subtitle {
  color: #77809a;
  font-size: 0.92rem;
}

.register-card .row {
  display: block;
}

.register-card .col-4,
.register-card .col-8 {
  width: 100%;
}

.register-card .col-4:empty {
  display: none;
}

.register-card .col-form-label {
  display: block;
  padding: 0 0 0.4rem;
  color: #39415c;
  font-size: 0.9rem;
  font-weight: 600;
}

.register-card .form-check {
  padding-top: 0.15rem;
}

.form-control {
  min-height: 46px;
  border-radius: 0.65rem;
  border: 1px solid #dce1ed;
  background-color: #fbfcff;
  transition: all 0.3s ease;
}

.form-control:focus {
  border-color: #667eea;
  box-shadow: 0 0 0 0.2rem rgba(102, 126, 234, 0.25);
}

.btn-primary {
  background-color: #667eea;
  border-color: #667eea;
  border-radius: 0.7rem;
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

@media (max-width: 480px) {
  .register-page {
    align-items: flex-start !important;
    padding: 1rem 0.75rem;
  }

  .card-body {
    padding: 1.5rem 1.25rem;
  }
}
</style>
