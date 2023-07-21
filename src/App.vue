<template>
  <div>
  <h2>Formulir siswa</h2>
  <form @submit.prevent="submitForm">
    <label for="nama">Nama:</label>
    <input type="text" id="nama" v-model="siswa.nama"><br>

    <label for="kelas">Kelas:</label>
    <input type="text" id="kelas" v-model="siswa.kelas"><br>

    <label for="alamat">Alamat:</label>
    <input type="textarea" id="alamat" v-model="siswa.alamat"><br>

    <label for="nilai mtk">Nilai MTK</label>
    <input type="number" id="nilai mtk" v-model="siswa.nilaimtk"><br>

    <label for="nilai inggris">Nilai inggris</label>
    <input type="number" id="nilai inggris" v-model="siswa.nilaiinggris"><br>

    <label for="nilai ipa"> Nilai Ipa</label>
    <input type="number" id="nilai ipa" v-model="siswa.nilaiipa"><br>

    <button type="submit">Simpan</button>
  </form>

  <div v-if="showResult">
  nama: {{ name }} <br>
    kelas: {{ kelas }} <br>
      alamat: {{ alamat }} <br>
        nilaimtk: {{ mtk }} <br>
          nilaiinggris: {{ ninggris }} <br>
            nilaiipa: {{ ipa }} <br>
              totalnilai: {{ total }} <br>
              keterangan: {{ keterangan }}
  </div>
   </div> 

</template>

<script>
import { ref } from 'vue';

export default {
  data() {
    return {
      siswa: {
        nama: '',
        kelas: '',
        alamat: '',
        nilaimtk: '',
        nilaiinggris: '',
        nilaiipa: ''
      },
      showResult: ref(false),
      name: ref(''),
      kelas: ref(''),
      alamat: ref(''),
      mtk: ref(''),
      inggris: ref(''),
      ipa: ref(''),
      total: 0,
      keterangan: ref(''),
    };
  },
  methods: {
    submitForm() {
      this.name = this.siswa.nama;
      this.kelas = this.siswa.kelas;
      this.alamat = this.siswa.alamat;
      this.mtk = this.siswa.nilaimtk;
      this.inggris = this.siswa.nilaiinggris;
      this.ipa = this.siswa.nilaiipa;
      this.total = parseInt(this.mtk) + parseInt(this.inggris) + parseInt(this.ipa);
      if (this.total > 240) {
        this.keterangan = "lulus"
      } else {
        this.keterangan = "tidak lulus"
      }
      this.showResult = true
  },
},
}
</script>