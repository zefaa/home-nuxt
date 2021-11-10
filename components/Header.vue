<template>
  <v-container class="mb-8">
    <v-app-bar
      :clipped-left="clipped"
      app
      color="#399cbd"
      :hide-on-scroll="scroll"
    >
      <!--tampilan bar title mobile-->
     <v-app-bar-title class="white--text hidden-md-and-up">YOGA</v-app-bar-title
      >

      <!--tampilan bar title desktop-->
      <v-app-bar-title class="white--text hidden-sm-and-down"
        >Yayasan Yohannes Gabriel Perwakilan 1</v-app-bar-title
      >
      <v-spacer />

      <!--tampilan menu mobile-->
      <span class="hidden-md-and-up">
        <v-btn @click.stop="drawer = !drawer" color="white">
          <v-icon>mdi-menu</v-icon>
        </v-btn>
      </span>

      <!--tampilan menu desktop-->
      <v-toolbar-items class="hidden-sm-and-down">
        <v-btn to="insta" text color="white">
          <v-icon>mdi-instagram</v-icon>
        </v-btn>

        <v-btn to="mail" text color="white">
          <v-icon>mdi-gmail</v-icon>
        </v-btn>

        <v-btn to="wa" text color="white">
          <v-icon>mdi-whatsapp</v-icon>
        </v-btn>

        <v-btn icon @click.stop="rightDrawer = !rightDrawer" color="white">
          <v-icon>mdi-information-outline</v-icon>
        </v-btn>
      </v-toolbar-items>
    </v-app-bar>

    <!--ini nav-bar buat informasi-->
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

    <!--ini navbar buat kontak-->
    <v-navigation-drawer v-model="drawer" right fixed>
      <v-list dense>
        <v-list-item
          v-for="item in items"
          :key="item.title"
          v-bind:href="item.link"
        >
          <v-list-item-content>
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
  </v-container>
</template>

<script>
export default {
  data() {
    return {
      clipped: false,
      drawer: false,
      items: [
        {
          title: "Instagram",
          link: "https://www.instagram.com/tv/CGrH7K1jAt6/",
          icon: "insta",
        },
        { title: "Gmail", link: "https://www.gmail.com", icon: "mail" },
        {
          title: "WhatsApp",
          link: "https://api.whatsapp.com/send?phone=62082132229796&text=Selamat%20pagi%2C%20saya%20ingin%20bertanya%20sesuatu%20apakah%20bisa%3F",
          icon: "wa",
        },
      ],

      scroll: true,

      miniVariant: false,
      right: true,
      rightDrawer: false,
      title2: "POSTING TERBARU",
    };
  },
};
</script>

