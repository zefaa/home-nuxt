<template>
  <v-app light>
    <v-main>
      <v-container class="mb-8">
        <!-- header-section ambil tampilan di assets scss -->
        <section class="header-section mx-auto">
          <v-app-bar
            :clipped-left="clipped"
            app
            color="#399cbd"
            :hide-on-scroll="scroll"
          >
            <!--tampilan bar title mobile-->
            <v-app-bar-title class="white--text hidden-md-and-up"
              >YOGA</v-app-bar-title
            >

            <!--tampilan bar title desktop-->
            <v-app-bar-title class="white--text hidden-sm-and-down"
              >Yayasan Yohannes Gabriel Perwakilan 1</v-app-bar-title
            >
            <v-spacer />

            <!--tampilan menu mobile-->
            <span class="hidden-md-and-up">
              <v-btn icon @click.stop="drawer = !drawer" color="white">
                <v-icon>mdi-dots-vertical-circle-outline</v-icon>
              </v-btn>
            </span>

            <!--tampilan menu desktop-->
            <v-toolbar-items class="hidden-sm-and-down">
              <v-btn
                text
                color="white"
                icon
                href="https://www.instagram.com/tv/CGrH7K1jAt6/"
              >
                <v-icon>mdi-instagram</v-icon>
              </v-btn>

              <v-btn text color="white" icon href="https://www.gmail.com">
                <v-icon>mdi-gmail</v-icon>
              </v-btn>

              <v-btn
                text
                color="white"
                icon
                href="https://api.whatsapp.com/send?phone=62082132229796&text=Selamat%20pagi%2C%20saya%20ingin%20bertanya%20sesuatu%20apakah%20bisa%3F"
              >
                <v-icon>mdi-whatsapp</v-icon>
              </v-btn>

              <v-btn
                icon
                @click.stop="rightDrawer = !rightDrawer"
                color="white"
              >
                <v-icon>mdi-information-outline</v-icon>
              </v-btn>
            </v-toolbar-items>
          </v-app-bar>

          <!--ini nav-bar buat informasi-->
          <v-navigation-drawer
            v-model="rightDrawer"
            :right="right"
            temporary
            fixed
          >
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
                    >Puncak Perayaan HUT 96 Yayasan Yohannes Gabriel, Siswa dan
                    Guru Bergembira Bersama Melalui Webinar dan Pengumuman
                    Lomba</a
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
                    >Perayaan 96 Tahun Yayaysan Yohannes Gabriel, Misa Syukur
                    dan Pemberian Penghargaan Masa Abdi</a
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
                    >Dalami Makna Visi-Misi Yayasan, Guru Baru Diajak Bermain
                    dalam Acara Pembinaan Guru Baru</a
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
                v-for="item in datas"
                :key="item.title"
                v-bind:href="item.link"
              >
                <v-list-item-content>
                  <v-list-item-title>{{ item.title }}</v-list-item-title>
                </v-list-item-content>
              </v-list-item>
            </v-list>
          </v-navigation-drawer>
        </section>

        <nuxt />
        
        <!-- footer-container ambil tampilan di assets main.scss -->
        <section class="footer-container pt-16 mt-16 white--text">
          <v-card
            flat
            tile
            width="100%"
            class="primary white--text text-center"
          >
            <v-card-text class="pt-0 text-left text-md-center">
              <v-expansion-panels accordion v-model="panel" multiple>
                <v-expansion-panel
                  v-for="(item, i) in items"
                  :key="i"
                  class="primary col-md-3 col-12 elevation-0"
                >
                  <h3 class="d-none d-md-block py-2 " >{{ item.name }}</h3>
                  <v-expansion-panel-header class="d-md-none white--text">{{
                    item.name
                  }}</v-expansion-panel-header>
                  <v-expansion-panel-content>
                    <li v-for="(tag, i) in item.tags" :key="i">
                      <a
                        target="_blank"
                        v-bind:href="tag.url"
                        class="white--text"
                        >{{ tag.urlname }}
                      </a>
                    </li>
                  </v-expansion-panel-content>
                </v-expansion-panel>
              </v-expansion-panels>
            </v-card-text>

            <v-divider></v-divider>

            <v-card-text class="white--text">
              Copyright @ - {{ new Date().getFullYear() }} Yohannes Gabriel
              Perwakilan 1 Surabaya, All Rights Reserved
            </v-card-text>
          </v-card>
        </section>
        <!-- akhir dari -->
      </v-container>
    </v-main>
  </v-app>
</template>

<script>
export default {
  data: () => ({
    
      clipped: false,
      drawer: false,
      items: [
        {
          title: "Instagram",
          link: "https://www.instagram.com/tv/CGrH7K1jAt6/",
          
        },
        { title: "Gmail", link: "https://www.gmail.com",},
        {
          title: "WhatsApp",
          link: "https://api.whatsapp.com/send?phone=62082132229796&text=Selamat%20pagi%2C%20saya%20ingin%20bertanya%20sesuatu%20apakah%20bisa%3F",
        
        },
      ],
      scroll: true,

      miniVariant: false,
      right: true,
      rightDrawer: false,
      title2: "POSTING TERBARU",
    
    panel: [],
    items: [
      {
        name: "Logo Yayasan Yohanes Gabriel Perwakilan 1",
        icon: "mdi-view-map-marker-outline",
        link: "https://codepen.io/jettaz",

        // tags: [
        //   {
        //     icon: "mdi-view-logo.jpeg",
        //     url: "https://codepen.io/jettaz",
        //   },
        // ],
      },

      {
        name: "Informasi Kontak",
        tags: [
          {
            icon: "mdi-view-map-marker-outline",
            urlname: "Jl. M H. Thamrin No.29-31, DR. Soetomo, Kec. Tegalsari",
            url: "https://www.google.com/maps/dir/-7.276548,112.7509655/Jl.+MH.+Thamrin+No.29-31,+DR.+Soetomo,+Kec.+Tegalsari/@-7.2776446,112.7368783,15z/data=!3m1!4b1!4m9!4m8!1m1!4e1!1m5!1m1!1s0x2dd7fbe98e929963:0x440f529f798ff7ba!2m2!1d112.7372793!2d-7.2817724",
          },
          {
            icon: "mdi-view-phone",
            urlname: "(031) 995 33993 | 0821 3222 9796",
            url: "https://api.whatsapp.com/send?phone=62082132229796&text=Selamat%20pagi%2C%20saya%20ingin%20bertanya%20sesuatu%20apakah%20bisa%3F",
          },
          {
            icon: "mdi-view-email",
            urlname: "humas@yohannesgabrielpw1.org",
            url: "https://www.gmail.com",
          },
          {
            icon: "mdi-view-search-web",
            urlname: "yohannesgabrielpw1.org",
            url: "https://yohannesgabrielpw1.org/",
          },
        ],
      },
      {
        name: "Jam Operasional",
        tags: [
          { urlname: "Senin : 07:00-13.00" },
          { urlname: "Selasa : 07:00-13.00" },
          { urlname: "Rabu : 07:00-13.00" },
          { urlname: "Kamis : 07:00-13.00" },
          { urlname: "Jumat : 07:00-13.00" },
          { urlname: "Sabtu : 07:00-12.00" },
        ],
      },
      {
        name: "Penghitung Pengunjung",
        tags: [{ urlname: "Help Center", url: "https://codepen.io/jettaz" }],
      },
    ],
  }),

  scroll: true,

  miniVariant: false,
  right: true,
  rightDrawer: false,
  title2: "POSTING TERBARU",

  beforeDestroy() {
    if (typeof window !== "undefined") {
      window.removeEventListener("resize", this.onResize, { passive: true });
    }
  },

  mounted() {
    this.onResize();
    window.addEventListener("resize", this.onResize, { passive: true });
  },

  methods: {
    onResize() {
      if (window.innerWidth >= 960) {
        this.panel = [...Array(4).keys()].map((k, i) => i);
      } else {
        this.panel = [];
      }
    },
  },
};
</script>

