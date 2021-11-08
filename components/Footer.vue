<template>
  <v-footer dark padless>
    <v-card flat tile width="100%" class="primary white--text text-center">
      <v-card-text>
          <v-btn icon href="https://www.instagram.com/tv/CGrH7K1jAt6/">
            <v-icon>mdi-instagram</v-icon>
          </v-btn>

          <v-btn icon href="https://www.gmail.com">
            <v-icon>mdi-gmail</v-icon>
          </v-btn>

          <v-btn
            icon
            href="https://api.whatsapp.com/send?phone=62082132229796&text=Selamat%20pagi%2C%20saya%20ingin%20bertanya%20sesuatu%20apakah%20bisa%3F"
          >
            <v-icon>mdi-whatsapp</v-icon>
          </v-btn>
        </v-card-text>

      <v-card-text class="pt-0 text-left text-md-center">
        <v-expansion-panels accordion v-model="panel" multiple>
          <v-expansion-panel
            v-for="(item, i) in items"
            :key="i"
            class="primary col-md-3 col-12 elevation-0"
          >
            <h3 class="d-none d-md-block py-2">{{ item.name }}</h3>
            <v-expansion-panel-header class="d-md-none">{{
              item.name
            }}</v-expansion-panel-header>
            <v-expansion-panel-content>
              <li v-for="(tag,i) in item.tags" :key="i">
                <a target="_blank" v-bind:href="tag.url" class="white--text"
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
  </v-footer>

</template>

<script>
export default{
data: () => ({
    panel: [],

    items: [
      {
        name: "Logo Yayasan Yohanes Gabriel Perwakilan 1",
        tags: [
          {
            icon: "mdi-view-logo.jpeg",
            url: "https://codepen.io/jettaz",
          },
        ],
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
        tags: [
          { urlname: "Help Center", url: "https://codepen.io/jettaz" }
        ],
      },
    ],
  }),
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

