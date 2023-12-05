<template>
  <div class="about-container">
    <div class="profile-info">
      <h1>Dwi Rif'an Kurniawan</h1>
      <p>NIM: 22106050073</p>
      <p>Hobi: Membuat Login dengan JavaScript</p>
    </div>
    <div class="hobby-image">
      <img src="./assets/fishing.jpg" alt="Hobi Memancing">
    </div>
  </div>
</template>

<style scoped>
.about-container {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  padding: 20px;
}

.profile-info {
  text-align: center;
  margin-bottom: 20px;
  color: #333;
}

h1 {
  font-size: 24px;
  margin-bottom: 10px;
}

p {
  font-size: 16px;
  margin: 0;
}

.hobby-image {
  width: 100%;
  max-width: 400px;
  overflow: hidden;
  border-radius: 8px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
  transition: transform 0.3s ease-in-out;
}

.hobby-image img {
  width: 100%;
  height: auto;
  border-radius: 8px;
}

.hobby-image:hover {
  transform: scale(1.1);
}
</style>
