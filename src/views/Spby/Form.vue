<template>
  <v-container class="my-5">
    <v-form class="px-3">
      <v-text-field label="Nomor" v-model="nomor"></v-text-field>
      <v-text-field label="Nilai" v-model="nilai"></v-text-field>
      <v-text-field label="Tanggal" v-model="tanggal"></v-text-field>
      <v-btn text class="success mx-0 mt-3" @click="submit">Simpan</v-btn>
    </v-form>
  </v-container>
</template>

<script>
export default {
  data() {
    return {
      nomor: "",
      nilai: "",
      tanggal: ""
    };
  },
  methods:{
      submit(){
          console.log("nomor: "+this.nomor +" nilai: "+this.nilai+ " tanggal: "+this.tanggal)
      }
  }
};
</script>