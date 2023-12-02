<template>
    <div class="container">
      <div class="row">
        <div class="mr40 mt20">
          <router-link to="/list-plannogram">
            <img src="../../assets/icons/back.svg">
          </router-link>
        </div>
        <div>
          <h1 class="m0">Detail Plannogram</h1>
          <p class="mt5 mb20 tc-green">Your plannogram details</p>
        </div>
      </div>
      <hr class="uline-grey">
      <div class="row">
        <!-- Bagian kiri untuk gambar plannogram -->
        <div class="plannogram-image-container">
          <!-- Gambar plannogram di sini -->
          <!-- Pastikan untuk mengganti dengan path yang sesuai -->
          <img src="@/assets/images/flashsale.png" alt="kiki" width="500" height="400">
        </div>
        <!-- Bagian kanan untuk detail plannogram -->
        <div class="plannogram-details">
          <div class="mt50">
            <p class="detail-title">Plannogram Name</p>
            <h2>HARI RAYA LEBARAN</h2>
          </div>
          <div class="mt10">
            <p class="detail-title">Broadcast Schedule: Senin</p>
          </div>
          <div class="mt10">
            <p class="detail-title">Plannogram Status</p>
            <label class="label-green">Active</label>
          </div>
          <div class="mt10">
            <p class="detail-title">Valid From</p>
            <label class="label-green">17-11-2023</label>
          </div>
          <div class="mt10">
            <p class="detail-title">Valid Until</p>
            <label class="label-green">23-11-2023</label>
          </div>
          <div class="mt10">
            <p class="detail-title-bold">Created by Admin 1</p>
          </div>
          <div class="mt10">
            <p class="detail-title-bold">Updated by Admin 2</p>
          </div>
          <div class="mt10">
            <p class="detail-title-bold">List Product</p>
            <ul>
              <li></li>
              <li></li>
            </ul>
          </div>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    name: 'detail-plannogram',
    // Anda bisa menambahkan data dan methods jika diperlukan
  }
  </script>
  
  <style>
  /* Tambahkan CSS di sini untuk styling komponen anda */
  .container {
    display: flex;
    flex-direction: column;
  }
  
  .row {
    display: flex;
  }
  
  .plannogram-image-container {
    flex: 1; /* Atur sesuai dengan rasio yang anda inginkan */
    /* Tambahkan styling untuk gambar jika diperlukan */
  }
  
  .plannogram-details {
    flex: 1; /* Atur sesuai dengan rasio yang anda inginkan */
    /* Tambahkan styling untuk detail plannogram */
  }
  
  .detail-title {
    font-weight: bold;
  }
  
  .label-green {
    color: green;
    /* Tambahkan lebih banyak styling untuk label */
  }
  
  /* Tambahkan lebih banyak CSS jika diperlukan */
  </style>
  