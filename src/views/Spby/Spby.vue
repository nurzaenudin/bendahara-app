<template>
  <v-container class="my-5">
    <v-btn text class="success" router to="/Spby/form">
      Tambah SPBY
<!--       <span>
        <router-link to="/Spby/form">Tambah</router-link>
      </span> -->
    </v-btn>
    <router-view></router-view>
    <v-card text class="pa-3" v-for="spby in spbys" :key="spby.nomor">
      <v-layout row wrap class="pa-3 spby" :class="spby.status">
        <v-flex>
          <div class="caption grey--text">Nomor SPBy</div>
          <div>{{spby.nomor}}</div>
        </v-flex>
        <v-flex>
          <div class="caption grey--text">Nilai</div>
          <div>{{spby.nilai}}</div>
        </v-flex>

        <v-flex>
          <div class="caption grey--text">Tanggal</div>
          <div>{{spby.tanggal}}</div>
        </v-flex>

        <v-flex>
          <div class="caption grey--text">Status</div>
          <div>
            <v-chip
              small
              default
              class="white--text caption my-2"
              :class="spby.status"
            >{{spby.status}}</v-chip>
          </div>
        </v-flex>
      </v-layout>
      <v-divider></v-divider>
      <!--       <v-card-title>Nomor SPBY</v-card-title>
      <v-card-text>{{spby.nomor}}</v-card-text>-->
    </v-card>
  </v-container>
</template>
<script>
export default {
  data: () => ({
    spbys: [
      {
        nomor: "123456",
        nilai: "100.000",
        tanggal: "1 Maret 2020",
        status: "complete"
      },
      {
        nomor: "234",
        nilai: "2.200.000",
        tanggal: "2 Maret 2020",
        status: "ongoing"
      },
      {
        nomor: "345",
        nilai: "33.300.000",
        tanggal: "3 Maret 2020",
        status: "overdue"
      }
    ]
  })
};
</script>
<style>
.spby.complete {
  border-left: 5px solid #3cd1c2;
}
.spby.ongoing {
  border-left: 5px solid orange;
}
.spby.overdue {
  border-left: 5px solid tomato;
}

.v-chip.complete {
  background: #3cd1c2 !important;
}
.v-chip.ongoing {
  background: orange !important;
}
.v-chip.overdue {
  background: tomato !important;
}
</style>