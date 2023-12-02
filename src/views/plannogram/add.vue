<template>
    <div>
        <div class="container">
            <div class="row">
                <div class="mr40 mt20">
                    <router-link to="/list-user">
                        <img src="../../assets/icons/back.svg">
                    </router-link>
                </div>
                <div>
                    <h1 class="m0">Add Plannogram</h1>
                    <p class="mt5 mb20 tc-green">Increase the visibility of promotional products in our store highlights</p>
                </div>
            </div>
            <hr class="uline-grey">
            <div class="mt30 row">
                <div class="w20">
                    <label class="form-label">Background Image</label>
                </div>
                <div class="w80">
            <!-- The stylized box for uploading files -->
            <div>
    <!-- Kotak unggah dengan background image -->
    <div class="upload-box" @click="triggerFileInput" :style="backgroundImageStyle">
      <!-- Jika tidak ada gambar yang dipilih, tampilkan ikon dan teks -->
      <div v-if="!selectedImage" class="upload-icon">
        <img src="data:image/png;base64,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" width="200" height="150">
      </div>
      <div v-if="!selectedImage" class="upload-text"></div>
    </div>
    <!-- Input file yang tersembunyi -->
    <input ref="fileInput" type="file" @change="onFileSelected" style="display: none;">
  </div>
  </div>
            </div>

            <div class="mt50 row">
                <div class="w20">
                    <label class="form-label">Plannogram Name</label>
                </div>
                <div class="w80">
                    <input
                        v-model="plannogramData.name"
                        class="form-text"
                        type="text"
                        placeholder="Masukkan Plannogram Name"
                    >
                </div>
            </div>
            <div class="mt30 row">
                <div class="w20">
                    <label class="form-label">Broadcast Schedule</label>
                </div>
                <div class="w80">
                    <input
                        class="form-text"
                        type="text"
                        placeholder="Pilih Hari"
                    >
                </div>
            </div>
            <div class="mt30 row">
                <div class="w20">
                    <label class="form-label">Valid From</label>
                </div>
                <div class="w80">
                    <input
                        class="form-text"
                        type="date"
                        placeholder="Masukkan Tanggal"
                    >
                </div>
            </div>
            <div class="mt30 row">
                <div class="w20">
                    <label class="form-label">Valid Until</label>
                </div>
                <div class="w80">
                    <input
                        class="form-text"
                        type="date"
                        placeholder="Masukkan Tanggal"
                    >
                </div>
            </div>
            <div class="mt30 row">
                <div class="w20">
                    <label class="form-label">List Product</label>
                </div>
                <div class="w80">
                    <input
                        class="form-text"
                        type="text"
                        placeholder="Pilih Product"
                    >
                </div>
            </div>
            </div>
            <div class="flex mt30">
    <!-- Gunakan @click bukan router-link untuk memanggil method -->
    <button class="bt-submit-green" @click="addPlannogram">Add Plannogram</button>
  </div>
        </div>
</template>

<script>
export default {
  data() {
    return {
        plannogramData: {
        selectedImage: null,
        name: '',
        schedule: '',
        validFrom: '',
        validUntil: '',
        productList: ''
      },
      selectedImage: null,
    };
  },
  computed: {
    // Menghitung style background image
    backgroundImageStyle() {
      // Jika ada gambar yang dipilih, gunakan sebagai background
      return this.selectedImage ? { backgroundImage: `url(${this.selectedImage})` } : {};
    }
  },
  methods: {
    triggerFileInput() {
      // Trigger klik pada input file ketika kotak unggah diklik
      this.$refs.fileInput.click();
    },
    onFileSelected(event) {
      const file = event.target.files[0];
      if (file) {
        const reader = new FileReader();
        reader.onload = e => {
          // Setelah berhasil dibaca, tetapkan sebagai latar belakang
          this.selectedImage = e.target.result;
          console.log(this.selectedImage); // Untuk debugging
        };
        reader.readAsDataURL(file);
      }
    },
    addPlannogram() {
      // Contoh: Simpan data ke dalam state management atau kirim ke server
      console.log(this.plannogramData);
      
      // Simulasikan penyimpanan data
      this.$store.dispatch('savePlannogram', this.plannogramData.name);

      // Setelah simpan, navigasikan ke halaman list
      this.$router.push('/list-plannogram');
    }
  }
}
</script>

<style>
.upload-box {
  /* Gaya untuk kotak unggah */
  width: 200px; /* Atau ukuran spesifik yang Anda inginkan */
  height: 150px; /* Atau tinggi spesifik yang Anda inginkan */
  background-size: cover;
  background-position: center;
  cursor: pointer;
  border: 2px solid grey;
  /* Tambahkan gaya lain sesuai kebutuhan */
}
</style>