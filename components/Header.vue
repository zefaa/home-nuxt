<template>
  <v-container>
    <v-app-bar
      :clipped-left="clipped"
      app
      color="#399cbd"
      :hide-on-scroll="scroll"
    >
      <v-app-bar-title class="white--text">Yayasan Yohannes Gabriel Perwakilan 1</v-app-bar-title>
      <v-spacer />
      
      <v-btn
        icon
        href="https://www.instagram.com/tv/CGrH7K1jAt6/"
        color="white"
      >
        <v-icon>mdi-instagram</v-icon>
      </v-btn>
      <v-btn icon href="https://www.gmail.com" color="white">
        <v-icon>mdi-gmail</v-icon>
      </v-btn>
      <v-btn
        icon
        href="https://api.whatsapp.com/send?phone=62082132229796&text=Selamat%20pagi%2C%20saya%20ingin%20bertanya%20sesuatu%20apakah%20bisa%3F"
        color="white"
      >
        <v-icon>mdi-whatsapp</v-icon>
      </v-btn>
      <v-btn icon @click.stop="rightDrawer = !rightDrawer" color="white">
        <v-icon>mdi-information-outline</v-icon>
      </v-btn>
      
    </v-app-bar>
    <v-navigation-drawer v-model="rightDrawer" :right="right" temporary fixed>
      <v-list-item>
        <v-list-item-content>
          <v-list-item-title v-text="title2" />
        </v-list-item-content>
      </v-list-item>

      <v-list-item>
        <v-list-item-content>
          <v-list-item-subtitle>
            <a
              href="https://yohannesgabrielpw1.org/puncak-perayaan-hut-96-yayasan-yohannes-gabriel-siswa-dan-guru-bergembira-bersama-melalui-webinar-dan-pengumuman-lomba/"
              >Puncak Perayaan HUT 96 Yayasan Yohannes Gabriel, Siswa dan Guru
              Bergembira Bersama Melalui Webinar dan Pengumuman Lomba</a
            ></v-list-item-subtitle
          >
          <p>29 Oktober 2021</p>
        </v-list-item-content>
      </v-list-item>

      <v-list-item>
        <v-list-item-content>
          <v-list-item-subtitle>
            <a
              href="https://yohannesgabrielpw1.org/perayaan-96-tahun-yayaysan-yohannes-gabriel-misa-syukur-dan-pemberian-penghargaan-masa-abdi/"
              >Perayaan 96 Tahun Yayaysan Yohannes Gabriel, Misa Syukur dan
              Pemberian Penghargaan Masa Abdi</a
            ></v-list-item-subtitle
          >
          <p>26 Oktober 2021</p>
        </v-list-item-content>
      </v-list-item>

      <v-list-item>
        <v-list-item-content>
          <v-list-item-subtitle>
            <a
              href="https://yohannesgabrielpw1.org/dalami-makna-visi-misi-yayasan-guru-baru-diajak-bermain-dalam-acara-pembinaan-guru-baru/"
              >Dalami Makna Visi-Misi Yayasan, Guru Baru Diajak Bermain dalam
              Acara Pembinaan Guru Baru</a
            ></v-list-item-subtitle
          >
          <p>13 Oktober 2021</p>
        </v-list-item-content>
      </v-list-item>
    </v-navigation-drawer>
  </v-container>
</template>

<script>
export default {
  data() {
    return {
      clipped: false,
      drawer: false,
      scroll: true,

      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: "Yayasan Yohanes Gabriel Perwakilan 1",
      title2: "POSTING TERBARU",
    };
  },
};
</script>

