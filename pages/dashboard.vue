<template>
  <div>
    <section class="dash1 mt-2 d-flex white--text text-h2">
      <h6 class="mx-auto my-auto text-center">
        MEWUJUDKAN PENDIDIKAN KATOLIK YANG MEMBENTUK PRIBADI BERINTEGRITAS
      </h6>
    </section>

    <section class="dash2 ma-auto pa-16">
      
      <center>
        <img src="@/assets/images/children.jpg" height="100" width="150" />
      </center>

      <p class="mx-auto my-auto text-center font-weight-bold">
        RD.Aloysius Hans Koerniawan
      </p>

      <p class="text-center">
        Ketua Yayasan Yohannes Gabriel Perwakilan 1 Surabaya
      </p>

      <p class="mx-auto my-auto justify">
        &nbsp; &nbsp; ”Selamat bergabung di website resmi kami, Yayasan Yohannes Gabriel
        Perwakilan 1.
      </p>
      <p class="mx-auto mb-auto pa-auto justify">
        Yayasan Yohannes Gabriel Perwakilan 1 Surabaya adalah
        yayasan pendidikan yang mengelola sekolah-sekolah Katolik di Keuskupan
        Surabaya. Sejak berdiri tahun 1925, yayasan ini ada dan terus memberikan
        yang terbaik untuk mencerdaskan kehidupan bangsa. Kami terus
        mengembangkan diri sesuai dengan gerak jaman agar dapat mendidik
        generasi penerus dan masa depan gereja dan masyarakat. Nilai-nilai
        Katolik dan kebangsaan menjadi pedoman utama dalam membina para siswa di
        sekolah-sekolah kami ini. Melalui media website berserta seluruh
        jejaring sosial yayasan, kami juga berharap agar sekolah-sekolah kami
        makin dikenal sebagai sekolah Katolik milik Keuskupan Surabaya yang
        dapat diandalkan. Terlebih juga agar para wali murid makin percaya
        dengan sekolah-sekolah kami dalam mendidik dan membina anak-anak.
        Silahkan menghubungi kami untuk segala informasi yang dibutuhkan.”
      </p>

      <h2
        class="mx-auto mt-auto pt-16 text-center font-weight-bold"
        width="100vw"
      >
        JADWAL KEGIATAN SEMINGGU
      </h2>

      <p class="mx-auto my-auto text-center font-weight-bold">
        SE-YAYASAN YOHANES GABRIEL
      </p>

      <!--Kalender-->

      <v-card color="rgb(255,250,250, 0.0) pr-10">
        <v-card-title class="justify-center text-h4 font-weight-bold">
          2021
        </v-card-title>
        <div
          class=" mx-lg-auto d-flex align-content-space-around flex-wrap"
        >
          <Card
            class="d-flex mx-auto text-center"
            v-for="(item, index) of events"
            :key="index"
            :item="item"
          ></Card>
        </div>
      </v-card>
    </section>

    <section class="ma-auto pa-16">
      <h2 class="mx-auto my-auto text-center font-weight-bold">
        TESTIMONI YOHANNES GABRIEL PERWAKILAN 1
      </h2>
      <p class="mx-auto mb-5 text-center font-weight-bold">
        SISWA, ORANGTUA, ALUMNI
      </p>

      <v-carousel class="px-auto mx-auto" cycle hide-delimiters show-arrows>
        <v-carousel-item
          v-for="(item, i) in items"
          :key="i"
          :src="item.src"
        ></v-carousel-item>
      </v-carousel>
    </section>
  </div>
</template>



<script>
import Card from "@/components/Card.vue";
export default {
  layout: "halaman",
  components: { Card },

  data: () => ({
    items: [
      {
        src: "https://cdn.vuetifyjs.com/images/carousel/squirrel.jpg",
      },
      {
        src: "https://cdn.vuetifyjs.com/images/carousel/sky.jpg",
      },
      {
        src: "https://cdn.vuetifyjs.com/images/carousel/bird.jpg",
      },
      {
        src: "https://cdn.vuetifyjs.com/images/carousel/planet.jpg",
      },
    ],

    events: [
      {
        name: "Pemilihan Ketua OSIS",
        description: "Dilaksanakan di SMAK Untung Suropati Sidoarjo",
        date: "8 November",
      },

      {
        name: "-",
        description: "",
        date: "9 November",
      },

      {
        name: "Hari Pahlawan",
        description: "Upacara dan Kegiatan Memperingati Hari Pahlawan ",
        date: "10 November",
      },

      {
        name: "Pertemuan Kepala Sekolah",
        description: "Dilaksanakan Secara Online",
        date: "11 November",
      },

      {
        name: "Puncak Acara SDK St. MAry Surabaya",
        description: "Lomba Fotografi dan Story Telling",
        date: "12 November",
      },

      {
        name: "-",
        description: "",
        date: "13 November",
      },
    ],
  }),

  computed: {
    // convert the list of events into a map of lists keyed by date
    eventsMap() {
      const map = {};
      this.events.forEach((e) => (map[e.date] = map[e.date] || []).push(e));
      return map;
    },
  },
  methods: {
    open(event) {
      alert(event.title);
    },
  },
};
</script>

<style scoped>
.dash1 {
  background-size: cover !important;
  width: 100%;
  height: 600px;
  background: url(@/assets/images/bash.jpeg);
}

.dash2 {
  background-size: cover;
  background-position: center;
  width: 100%;
  height: 100%;
  background-color: rgb(248, 248, 248);
}

.dash3 {
  background-size: cover !important;
  background-position: center;
  width: 100%;
  height: 100%;
  background: url(@/assets/images/bash1.jpeg);
}
</style>



