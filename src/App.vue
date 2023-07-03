<template>
  <div id="app">
    <nav class="navbar navbar-expand-lg navbar-dark bg-dark">
      <div class="container">
        <router-link to="/" class="navbar-brand">COMICS STORE</router-link>
        <ul class="navbar-nav ml-auto">
          <li class="nav-item">
            <router-link to="/" class="nav-link">Home</router-link>
          </li>
          <li class="nav-item">
            <router-link to="/books" class="nav-link">Buku</router-link>
          </li>
          <li class="nav-item">
            <router-link to="/categories" class="nav-link">Kategori</router-link>
          </li>
          <li class="nav-item">
            <router-link to="/Member" class="nav-link">Anggota</router-link>
          </li>
          <li class="nav-item">
            <router-link to="/Peminjaman" class="nav-link">Peminjaman</router-link>
          </li>
        </ul>
      </div>
    </nav>
    <div class="container mt-4">
      <router-view></router-view>
    </div>
  </div>
</template>

<script>
export default {
  name: 'App',
};
</script>

<style>
#app {
  font-family: Arial, Helvetica, sans-serif;
}
</style>
