<template>
  <div>
    <section class="dash1 mt-2 d-flex white--text">
        <h1 class="mx-auto my-auto text-center">
          MEWUJUDKAN PENDIDIKAN KATOLIK YANG MEMBENTUK PRIBADI BERINTEGRITAS
        </h1>
    </section>

    <section class="dash2">
      
        <center>
          <img src="@/assets/images/children.jpg" height="100" width="150" />
        </center>

        <center><h4>RD.Aloysius Hans Koerniawan</h4></center>
        <center>
          <p class="justify-center">
            Ketua Yayasan Yohannes Gabriel Perwakilan 1 Surabaya
          </p>
        </center>
     

      <v-col class="pa-md-2 mx-lg-auto mb-8">
        <center>
          <p class="text-h20">
            ” Selamat bergabung di website resmi kami, Yayasan Yohannes Gabriel
            Perwakilan 1.
          </p>
          <p class="text-h10">
            &nbsp; &nbsp; Yayasan Yohannes Gabriel Perwakilan 1 Surabaya adalah
            yayasan pendidikan yang mengelola sekolah-sekolah Katolik di
            Keuskupan Surabaya. Sejak berdiri tahun 1925, yayasan ini ada dan
            terus memberikan yang terbaik untuk mencerdaskan kehidupan bangsa.
            Kami terus mengembangkan diri sesuai dengan gerak jaman agar dapat
            mendidik generasi penerus dan masa depan gereja dan masyarakat.
            Nilai-nilai Katolik dan kebangsaan menjadi pedoman utama dalam
            membina para siswa di sekolah-sekolah kami ini. Melalui media
            website berserta seluruh jejaring sosial yayasan, kami juga berharap
            agar sekolah-sekolah kami makin dikenal sebagai sekolah Katolik
            milik Keuskupan Surabaya yang dapat diandalkan. Terlebih juga agar
            para wali murid makin percaya dengan sekolah-sekolah kami dalam
            mendidik dan membina anak-anak. Silahkan menghubungi kami untuk
            segala informasi yang dibutuhkan.”
          </p>
        </center>
      </v-col>

      <v-col class="mt-2">
        <center>
          <h1 justify-center>JADWAL KEGIATAN SEMINGGU</h1>
          <h2>SE-YAYASAN YOHANES GABRIEL</h2>
        </center>
      </v-col>

      <v-col>
        <v-card class="pa-md-4 mx-lg-auto" color="rgb(255,250,250, 0.0)">
          <v-card
            ><center><h1>NOVEMBER</h1></center></v-card>
          <v-flex>
            <v-card>
              <v-calendar :now="today" :value="today" color="primary">
                <template v-slot:day="{ date }">
                  <template v-for="event in eventsMap[date]">
                    <v-menu :key="event.title" v-model="event.open">
                      <template v-slot:activator="{ on }">
                        <div
                          v-if="!event.time"
                          v-ripple
                          class="my-event"
                          v-on="on"
                          v-html="event.title"
                        ></div>
                      </template>
                    </v-menu>
                  </template>
                </template>
              </v-calendar>
            </v-card>
          </v-flex>
        </v-card>
      </v-col>
    </section>

    <section>
      <v-col>
        <center>
          <h1 justify-center>TESTIMONI YOHANNES GABRIEL PERWAKILAN 1</h1>
          <h2 justify-center><p class="text">SISWA, ORANGTUA, ALUMNI</p></h2>
        </center>
      </v-col>
      <v-col>
        <v-carousel hide-delimiters>
          <v-carousel-item
            v-for="(item, i) in items"
            :key="i"
            :src="item.src"
          ></v-carousel-item>
        </v-carousel>
      </v-col>
    </section>
  </div>
</template>



<script>
export default {
  layout: "halaman",

  data: () => ({
    today: "2021-11-09",
    events: [
      {
        title: "Orasi Pemilihan Ketua OSIS SMAK Untung Suropati Sidoarjo",
        date: "2021-11-08",
      },
      {
        title: "Hari Guru",
        date: "2021-11-25",
      },
    ],

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



