<template>
  <div>
    <h1>List Peminjaman DIPINJAM</h1>
    <table class="table">
      <thead>
      <tr>
        <th>ID</th>
        <th>Tanggal Peminjaman</th>
        <th>Nomor Anggota</th>
        <th>Status Peminjaman</th>
        <th>Tanggal Pengembalian</th>
        <th>Durasi Keterlambatan</th>
      </tr>
      </thead>
      <tbody>
      <tr v-for="peminjaman in peminjamanDipinjam" :key="peminjaman.id">
        <td>{{ peminjaman.id }}</td>
        <td>{{ peminjaman.tanggal_peminjaman }}</td>
        <td>{{ peminjaman.nomor_anggota }}</td>
        <td>{{ peminjaman.status_peminjaman }}</td>
        <td>{{ peminjaman.tanggal_pengembalian }}</td>
        <td>{{ peminjaman.durasi_keterlambatan }}</td>
      </tr>
      </tbody>
    </table>

    <h1>List Peminjaman DIKEMBALIKAN</h1>
    <table class="table">
      <thead>
      <tr>
        <th>ID</th>
        <th>Tanggal Peminjaman</th>
        <th>Nomor Anggota</th>
        <th>Status Peminjaman</th>
        <th>Tanggal Pengembalian</th>
        <th>Durasi Keterlambatan</th>
      </tr>
      </thead>
      <tbody>
      <tr v-for="peminjaman in peminjamanDikembalikan" :key="peminjaman.id">
        <td>{{ peminjaman.id }}</td>
        <td>{{ peminjaman.tanggal_peminjaman }}</td>
        <td>{{ peminjaman.nomor_anggota }}</td>
        <td>{{ peminjaman.status_peminjaman }}</td>
        <td>{{ peminjaman.tanggal_pengembalian }}</td>
        <td>{{ peminjaman.durasi_keterlambatan }}</td>
      </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
import axios from 'axios';

export default {
  name: 'App',
  data() {
    return {
      peminjamanDipinjam: [],
      peminjamanDikembalikan: [],
    };
  },
  mounted() {
    // Mengambil data peminjaman dengan status DIPINJAM dari API backend PHP
    this.fetchPeminjamanDipinjam();

    // Mengambil data peminjaman dengan status DIKEMBALIKAN dari API backend PHP
    this.fetchPeminjamanDikembalikan();
  },
  methods: {
    fetchPeminjamanDipinjam() {
      // Panggil API backend PHP untuk mendapatkan data peminjaman dengan status DIPINJAM
      // Gantikan BASE_URL dengan URL API Anda
      axios.get('http://localhost/crud/statusdipinjam.php')
          .then((response) => {
            this.peminjamanDipinjam = response.data;
          })
          .catch((error) => {
            console.error(error);
          });
    },
    fetchPeminjamanDikembalikan() {
      // Panggil API backend PHP untuk mendapatkan data peminjaman dengan status DIKEMBALIKAN
      // Gantikan BASE_URL dengan URL API Anda
      axios.get( 'http://localhost/crud/statusdikembalikan.php')
          .then((response) => {
            this.peminjamanDikembalikan = response.data;
          })
          .catch((error) => {
            console.error(error);
          });
    },
  },
};
</script>