<template>
  <!-- Using Bootstrap's Header template (starter code) -->
  <!-- https://getbootstrap.com/docs/5.0/examples/headers/ -->
  <div class="container">
    <header class="d-flex justify-content-center py-3">
      <ul class="nav nav-pills">
        <li class="nav-item">
          <router-link to="/" class="nav-link" active-class="active" aria-current="page"
            >Home (Week 5)</router-link
          >
        </li>
        <li class="nav-item">
          <router-link to="/addBook" class="nav-link" active-class="active">AddBook</router-link>
        </li>
        <li class="nav-item">
          <router-link to="/member" class="nav-link" active-class="active">About</router-link>
        </li>
        <li class="nav-item">
          <router-link to="/getBookCount" class="nav-link" active-class="active">Get Book Count</router-link>
        </li>
        <li class="nav-item">
          <router-link to="/weatherView" class="nav-link" active-class="active">WeatherView</router-link>
        </li>
        <li class="nav-item">
          <router-link to="/countBookAPI" class="nav-link" active-class="active">Count Book API</router-link>
        </li>
        <li v-if="!isLogin">
          <router-link to="/firebaseSignin" class="nav-link" active-class="active">FirebaseSignIn</router-link>
        </li>
        <li v-if="isLogin">
          <router-link to="/logout" class="nav-link" active-class="active" @click="logout">FirebaseLogout</router-link>
        </li>
      </ul>
    </header>
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue';

const isLogin = ref(false);

onMounted(() => {
  const authenticated = localStorage.getItem('isAuthenticated');
  isLogin.value = authenticated;
});
</script>
<style scoped>
.b-example-divider {
  height: 3rem;
  background-color: rgba(0, 0, 0, 0.1);
  border: solid rgba(0, 0, 0, 0.15);
  border-width: 1px 0;
  box-shadow:
    inset 0 0.5em 1.5em rgba(0, 0, 0, 0.1),
    inset 0 0.125em 0.5em rgba(0, 0, 0, 0.15);
}

.form-control-dark {
  color: #fff;
  background-color: var(--bs-dark);
  border-color: var(--bs-gray);
}
.form-control-dark:focus {
  color: #fff;
  background-color: var(--bs-dark);
  border-color: #fff;
  box-shadow: 0 0 0 0.25rem rgba(255, 255, 255, 0.25);
}

.bi {
  vertical-align: -0.125em;
  fill: currentColor;
}

.text-small {
  font-size: 85%;
}

.dropdown-toggle {
  outline: 0;
}
</style>
