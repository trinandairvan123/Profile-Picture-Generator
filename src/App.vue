<template>
  <div class="container">
    <input v-model="text" type="text" placeholder="Masukkan teks" />
    <button @click="generateAvatar">Generate Avatar</button>
    <img v-if="avatarUrl" :src="avatarUrl" alt="Avatar" />
  </div>
</template>

<script>
export default {
  data() {
    return {
      text: "",
      avatarUrl: ""
    };
  },
  methods: {
    generateAvatar() {
      this.avatarUrl = `https://robohash.org/${this.text}`;
    }
  }
};
</script>

<style>
.container {
  display: flex;
  flex-direction: column;
  align-items: center;
}

input {
  margin-bottom: 10px;
  padding: 10px;
  font-size: 16px;
  border: 1px solid #ccc;
}

button {
  padding: 10px 20px;
  font-size: 16px;
  border: none;
  background-color: #4caf50;
  color: #fff;
  cursor: pointer;
}

button:hover {
  background-color: #46a049;
}

img {
  width: 200px;
  height: 200px;
  border-radius: 50%;
  margin-top: 10px;
}
</style>
