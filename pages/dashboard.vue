<template>
  <v-container class="pa-md-4 mx-lg-auto">
    <v-row no-gutters>
      <v-col>
        <v-card class="pa-md-2 mx-lg-auto">
          <center>
            <h1 justify-center>
              MEWUJUDKAN PENDIDIKAN KATOLIK YANG MEMBENTUK PRIBADI BERINTEGRITAS
            </h1>
          </center>
        </v-card>
      </v-col>
    </v-row>

    <v-row no-gutters>
      <v-col class="pa-md-2 mx-lg-auto">
        <center>
          <img src="@/assets/images/children.jpg" height="100" width="150"/>      
      
        </center>
        <v-card class="pa-1" outlined tile>
          <center><h4>RD.Aloysius Hans Koerniawan</h4></center>
          <center>
            <p class="justify-center">
              Ketua Yayasan Yohannes Gabriel Perwakilan 1 Surabaya
            </p>
          </center>
        </v-card>
      </v-col>
      <v-col class="pa-md-2 mx-lg-auto">
        <v-card>
          <p class="text-h7 justify-center">
            ” Selamat bergabung di website resmi kami, Yayasan Yohannes Gabriel
            Perwakilan 1.
          </p>
          <p class="justify-center">
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
        </v-card>
      </v-col>
    </v-row>

    <v-row no-gutters>
      <v-col class="pa-md-2 mx-lg-auto">
        <v-card class="pa-md-4 mx-lg-auto">
          <center>
            <h1 justify-center>
              <p class="text-h3">JADWAL KEGIATAN SEMINGGU</p>
            </h1>
            <p class="text-h5 justify-center">SE-YAYASAN YOHANES GABRIEL</p>
          </center>
        </v-card>
      </v-col>
    </v-row>

    <v-row no-gutters>
      <v-col class="pa-md-2 mx-lg-auto">
        <v-card class="pa-md-4 mx-lg-auto">
          <center>
            <h1 justify-center><p class="text">NOVEMBER</p></h1>
          </center>
        </v-card>
      </v-col>
    </v-row>

    <v-flex class="pa-md-2 mx-lg-auto">
      <v-card>
        <v-calendar :now="today" :value="today" color="primary">
          <template v-slot:day="{ date }">
            <template v-for="event in eventsMap[date]">
              <v-menu
                :key="event.title"
                v-model="event.open"
                
              >
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

    <v-row no-gutters>
      <v-col class="pa-md-2 mx-lg-auto">
        <v-card class="pa-md-4 mx-lg-auto">
          <center>
            <h1 justify-center>
              <p class="text">TESTIMONI YOHANNES GABRIEL PERWAKILAN 1</p>
            </h1>
            <h2 justify-center><p class="text">SISWA, ORANGTUA, ALUMNI</p></h2>
          </center>
        </v-card>
      </v-col>
    </v-row>

    <v-row no-gutters>
      <v-col class="pa-md-2 mx-lg-auto">
        <v-carousel hide-delimiters>
            
          <v-carousel-item
            v-for="(item, i) in items"
            :key="i"
            :src="item.src"
          ></v-carousel-item>
        </v-carousel>
      </v-col>
    </v-row>
  </v-container>
</template>



<script>
export default {
  layout: "halaman",

  data: () => ({
    today: "2021-11-08",
    events: [
      {
        title: "Vacation",
        date: "2021-11-01",
      },
      {
        title: "Vacation",
        date: "2021-11-02",
      },
      {
        title: "Vacation",
        date: "2021-11-03",
      },
      {
        title: "Meeting",
        date: "2021-11-08",
      },
      {
        title: "30th Birthday",
        date: "2021-11-19",
      },
      {
        title: "Vacation",
        date: "2021-11-22",
      },
      {
        title: "Conference",
        date: "2021-11-25",
      },
      {
        title: "Hackathon",
        date: "2021-11-28",
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


