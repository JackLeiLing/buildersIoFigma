<template>
  <div class="login-wrapper">
    <v-app-bar
      color="#281FA5"
      class="header"
    >
      <v-toolbar-title class="header-content">
        <div class="header-title">Parent Portal</div>
        <div class="header-subtitle">ASTP</div>
      </v-toolbar-title>
    </v-app-bar>

    <v-container class="login-container">
      <v-row justify="center">
        <v-col cols="12" sm="8" md="6" lg="4">
          <v-form class="login-form">
            <div class="form-field">
              <label class="field-label">User Name</label>
              <v-text-field
                v-model="username"
                variant="outlined"
                density="comfortable"
                hide-details
                class="input-field"
              ></v-text-field>
            </div>

            <div class="form-field">
              <label class="field-label">Password</label>
              <v-text-field
                v-model="password"
                type="password"
                variant="outlined"
                density="comfortable"
                hide-details
                class="input-field"
              ></v-text-field>
            </div>

            <div class="button-wrapper">
              <v-btn
                color="#08F"
                class="login-btn"
                @click="handleLogin"
              >
                Login
              </v-btn>
            </div>
          </v-form>
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const username = ref('')
const password = ref('')

const handleLogin = () => {
  console.log('Login clicked', { username: username.value, password: password.value })
}
</script>

<style scoped>
.login-wrapper {
  min-height: 100vh;
  background: #fff;
}

.header {
  height: 70px !important;
}

.header-content {
  display: flex;
  flex-direction: column;
  gap: 2px;
  padding: 10px 0;
}

.header-title {
  color: #fff;
  font-size: 17px;
  font-weight: 590;
  line-height: 22px;
  letter-spacing: -0.41px;
}

.header-subtitle {
  color: #f2f2f7;
  font-size: 15px;
  font-weight: 400;
  line-height: 20px;
  letter-spacing: -0.45px;
}

.login-container {
  padding-top: 180px;
  max-width: 100%;
}

.login-form {
  display: flex;
  flex-direction: column;
  gap: 34px;
  padding: 0 20px;
}

.form-field {
  display: flex;
  flex-direction: column;
  gap: 8px;
}

.field-label {
  color: rgba(30, 30, 30, 1);
  font-size: 16px;
  font-weight: 400;
  line-height: 140%;
}

.input-field :deep(.v-field) {
  border-radius: 8px;
  border-color: rgba(217, 217, 217, 1);
  background: rgba(255, 255, 255, 1);
  min-height: 46px;
}

.input-field :deep(.v-field__input) {
  padding: 12px 16px;
  min-height: 46px;
}

.button-wrapper {
  display: flex;
  justify-content: center;
  margin-top: 36px;
}

.login-btn {
  border-radius: 1000px;
  padding: 4px 10px;
  height: 28px;
  min-width: 58px;
  font-size: 15px;
  font-weight: 400;
  line-height: 20px;
  letter-spacing: -0.23px;
  text-transform: none;
}

@media (max-width: 600px) {
  .login-container {
    padding-top: 140px;
  }

  .login-form {
    padding: 0 16px;
  }
}

@media (min-width: 960px) {
  .login-container {
    padding-top: 200px;
  }
}
</style>
