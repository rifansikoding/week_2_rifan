<template>
  <div class="home">
    <header class="header">
      <h1>Welcome to My Awesome Website</h1>
      <p>Discover the Beauty of Vue.js</p>
    </header>

    <main class="main">
      <section class="description-section">
        <h2>What's Special About Our Website?</h2>
        <p>
          Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
        </p>
        <p>
          Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
        </p>
      </section>

      <section class="create-description-section">
        <h2>Create Your Own Description</h2>
        <textarea v-model="userDescription" placeholder="Type your description here"></textarea>
      </section>
    </main>
  </div>
</template>

<script>
export default {
  data() {
    return {
      userDescription: ""
    };
  }
};
</script>

<style scoped>
.home {
  text-align: center;
  padding: 20px;
}

.header {
  background-color: #42b983;
  color: white;
  padding: 20px;
  border-radius: 10px;
}

.main {
  margin-top: 20px;
}

.description-section {
  max-width: 600px;
  margin: auto;
}

.create-description-section {
  margin-top: 20px;
}

textarea {
  width: 100%;
  padding: 10px;
  border: 1px solid #ccc;
  border-radius: 5px;
  margin-top: 10px;
}
</style>
