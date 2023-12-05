<template>
  <div class="flex flex-col container mx-auto p-4 gap-10">
    <!--Header-->
    <div class="flex justify-between border-b-2 pb-4 mb-4">
      <!--Menu-->
      <div class="flex gap-4">
        <router-link class="hover:text-blue-500" to="/">Home</router-link>
        <router-link class="hover:text-blue-500" to="/about">About</router-link>
        <router-link v-if="auth.username" class="hover:text-blue-500" to="/restricted">Restricted Page</router-link>
        <p v-else @click="showAlert" class="cursor-pointer hover:underline">Restricted Page</p>
      </div>
      <!--Authenticated User-->
      <div class="flex gap-2 items-center">
        <p v-if="auth.username">{{ auth.username }}</p>
        <div v-if="auth.username">
          <button class="bg-red-500 text-white py-1 px-3" @click="onLogout">Logout</button>
        </div>
        <div v-else>
          <router-link class="bg-blue-500 text-white py-1 px-3" to="/login">Login</router-link>
        </div>
      </div>
    </div>
    <!--Body-->
    <router-view></router-view>
  </div>
</template>

<script setup lang="ts">
import { useRouter } from "vue-router";
import { useAuthStore } from "@/stores/auth";

const auth = useAuthStore();
const router = useRouter();

const onLogout = () => {
  auth.logout();
  router.push("/login");
};

const showAlert = () => {
  alert("Anda harus login untuk mengakses halaman ini!");
};
</script>

<style scoped>
/* Styling for the entire page */
.container {
  max-width: 800px;
  margin: auto;
}

/* Styling for links and buttons */
a {
  text-decoration: none;
  color: #333;
  transition: color 0.3s;
}

a:hover {
  color: #007bff;
}

/* Additional styling for cursor pointer and underline on hover */
.cursor-pointer {
  cursor: pointer;
}

.hover:underline:hover {
  text-decoration: underline;
}

/* Styling for the border and padding on header */
.border-b-2 {
  border-bottom: 2px solid #ccc;
}

.pb-4 {
  padding-bottom: 1rem;
}

/* Styling for the Logout button */
.bg-red-500 {
  background-color: #d9534f;
}

.bg-blue-500 {
  background-color: #5bc0de;
}
</style>
