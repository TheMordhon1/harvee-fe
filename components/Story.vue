<template lang="">
  <section class="container px-5 md:px-0 mx-auto pt-24" id="story">
    <div class="flex justify-between items-center">
      <div class="w-auto">
        <h2 class="text-xl text-gray-900 mb-8">
          Kata Mereka <br />
          Tentang <span class="text-2xl font-bold">Harveee</span>
        </h2>
      </div>
    </div>
    <div class="flex mb-10">
      <div class="hidden lg:block lg:w-2/12 flex justify-center items-start">
        <img src="testimonial-line.svg" alt="" />
      </div>
      <div class="w-full lg:w-8/12 mt-16">
        <h2 class="text-xl text-gray-900 font-light">
          “Harveee adalah suatu terobosan bagi dunia pertanian di Indonesia.
          <br />
          Harveee akan memainkan peranan penting dalam melengkapi,
          memberdayakan, dan menyiapkan para petani kita dalam menyambut
          tantangan dan kesempatan yang akan muncul dalam Revolusi Industri
          Keempat. ”
        </h2>
        <div class="testimonial-info mt-8">
          <div class="name text-xl font-semibold">Siti Nur Aminah</div>
          <div class="title text-xl font-light text-gray-400">
            Project Manager
          </div>
        </div>
        <div class="testimonial-icon mt-10">
          <img
            src="testimonial-1-icon.png"
            alt=""
            class="w-20 mr-5 inline-block testimonial-user rounded-full"
          />
          <img
            src="testimonial-2-icon.png"
            alt=""
            class="w-20 mr-5 inline-block testimonial-user rounded-full"
          />
          <img
            src="testimonial-3-icon.png"
            alt=""
            class="w-20 mr-5 inline-block testimonial-user active rounded-full"
          />
        </div>

        <!-- <v-app>
          <v-carousel
            cycle
            height="400"
            hide-delimiter-background
            show-arrows-on-hover
          >
            <v-carousel-item v-for="(slide, i) in slides" :key="i">
              <v-sheet height="100%" class="px-10">
                <v-row class="fill-height" align="center" justify="center">
                  <div class="text-p" width="60%">{{ slide }} Slide</div>
                </v-row>
              </v-sheet>
            </v-carousel-item>
          </v-carousel>
        </v-app> -->
      </div>
      <div class="hidden lg:w-2/12"></div>
    </div>
  </section>
</template>
<script>
export default {
  data() {
    return {
      colors: [
        "indigo",
        "warning",
        "pink darken-2",
        "red lighten-1",
        "deep-purple accent-4",
      ],
      slides: [
        "Saya merasa terbantu sekali bekerjasama dengan TaniFund. Sekarang saya dapat memberdayakan anggota kelompok jauh lebih maksimal lagi untuk mengelola pertanian. Tim TaniFund juga mengajarkan mengenai sistem pertanian modern di era digital.",
        "Sebagai petani, saya dapat jauh lebih percaya diri karena selain mendapat pendanaan, TaniFund juga membantu dalam berbagi pengalaman dan edukasi.",
        "Alhamdulillah sejak bergabung dengan TaniFund, para petani di Cidaun kini semakin tenang karena bisa bertani dengan lahan yang lebih luas karena dapat permodalan. serta akses pasar menjadi lebih mudah dan sudah pasti.",
      ],
    };
  },
};
</script>
<style lang=""></style>
