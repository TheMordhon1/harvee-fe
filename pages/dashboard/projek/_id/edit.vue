<template lang="">
  <div class="project-page">
    <section class="dashboard-header pt-5">
      <div class="container mx-auto relative">
        <Navbar2 />
      </div>
    </section>

    <section class="container px-5 md:px-0 mx-auto pt-8 lg:mt-10 mt-5">
      <div class="w-full mr-6">
        <h2 class="text-2xl lg:text-4xl text-gray-900 mb-2 font-medium">
          Dashboard
        </h2>
      </div>
      <div class="w-full mr-6">
        <h3 class="text-xl lg:text-2xl text-gray-900 mb-4 capitalize">
          edit proyek "{{ campaign.data.name }}"
        </h3>
      </div>
      <!-- Button Action -->
      <div class="flex gap-2 mb-4 justify-end sticky">
        <nuxt-link
          :to="{
            name: 'dashboard-projek-id',
            params: { id: campaign.data.id },
          }"
          class="
            bg-button-green
            text-white
            font-bold
            px-6
            py-2
            rounded
            inline-flex
            items-center
            opacity-50
            hover:opacity-100
          "
        >
          Kembali
        </nuxt-link>
        <button
          @click="save"
          class="
            bg-button
            text-white
            font-bold
            px-6
            py-2
            rounded
            inline-flex
            items-center
          "
        >
          Simpan
        </button>
      </div>
      <hr class="lg:hidden block my-5" />
      <div class="block mb-2">
        <div class="w-full lg:max-w-full lg:flex mb-4">
          <div
            class="
              w-full
              lg:border
              border-gray-400
              bg-white
              rounded
              lg:p-8
              flex flex-col
              justify-between
              leading-normal
            "
          >
            <form class="w-full">
              <div class="flex flex-wrap -mx-3 mb-6">
                <div class="w-full md:w-1/2 px-3 mb-6 md:mb-0">
                  <label
                    class="
                      block
                      uppercase
                      tracking-wide
                      text-gray-700 text-xs
                      font-bold
                      mb-2
                    "
                  >
                    Nama Proyek
                  </label>
                  <input
                    class="
                      appearance-none
                      block
                      w-full
                      bg-gray-200
                      text-gray-700
                      border border-gray-200
                      rounded
                      py-3
                      px-4
                      leading-tight
                      focus:outline-none focus:border-gray-500
                    "
                    type="text"
                    placeholder="ex: Projek Porang Pak Dudi"
                    v-model="campaign.data.name"
                  />
                </div>
                <div class="w-full mb-4 md:w-1/2 px-3">
                  <label
                    class="
                      block
                      uppercase
                      tracking-wide
                      text-gray-700 text-xs
                      font-bold
                      mb-2
                    "
                  >
                    Total Biaya Proyek
                  </label>
                  <input
                    class="
                      appearance-none
                      block
                      w-full
                      text-gray-700
                      border border-gray-200
                      rounded
                      py-3
                      px-4
                      leading-tight
                      focus:outline-none
                    "
                    type="number"
                    placeholder="60000000"
                    v-model.number="campaign.data.goal_amount"
                    readonly
                  />
                  <small class="text-gray-400"
                    >*silahkan hubungi admin jika ingin mengubahnya</small
                  >
                </div>

                <div class="w-full mb-4 px-3">
                  <label
                    class="
                      block
                      uppercase
                      tracking-wide
                      text-gray-700 text-xs
                      font-bold
                      mb-2
                      mt-3
                    "
                  >
                    Keterangan Singkat
                  </label>
                  <input
                    class="
                      appearance-none
                      block
                      w-full
                      bg-gray-200
                      text-gray-700
                      border border-gray-200
                      rounded
                      py-3
                      px-4
                      mb-3
                      leading-tight
                      focus:outline-none focus:border-gray-500
                    "
                    type="text"
                    placeholder="Deskripsi singkat mengenai projectmu"
                    v-model="campaign.data.short_description"
                  />
                </div>

                <div class="w-full mb-4 px-3">
                  <label
                    class="
                      block
                      uppercase
                      tracking-wide
                      text-gray-700 text-xs
                      font-bold
                      mb-2
                      mt-3
                    "
                  >
                    Alamat
                  </label>
                  <input
                    class="
                      appearance-none
                      block
                      w-full
                      bg-gray-200
                      text-gray-700
                      border border-gray-200
                      rounded
                      py-3
                      px-4
                      mb-3
                      leading-tight
                      focus:outline-none focus:border-gray-500
                    "
                    type="text"
                    placeholder="Deskripsi singkat mengenai projectmu"
                    v-model="campaign.data.address"
                  />
                </div>

                <div class="w-full mb-4 md:w-1/2 px-3">
                  <label
                    class="
                      block
                      uppercase
                      tracking-wide
                      text-gray-700 text-xs
                      font-bold
                      mb-2
                    "
                  >
                    Minimal Pembiayaan
                  </label>
                  <input
                    class="
                      appearance-none
                      block
                      w-full
                      text-gray-700
                      border border-gray-200
                      rounded
                      py-3
                      px-4
                      leading-tight
                      focus:outline-none
                    "
                    type="number"
                    placeholder="100000"
                    v-model.number="campaign.data.min_pembayaran"
                    readonly
                  />
                  <small class="text-gray-400"
                    >*silahkan hubungi admin jika ingin mengubahnya</small
                  >
                </div>

                <div class="w-full mb-4 px-3">
                  <label
                    class="
                      block
                      uppercase
                      tracking-wide
                      text-gray-700 text-xs
                      font-bold
                      mb-2
                    "
                  >
                    Yang anda tawarkan kepada funder
                  </label>
                  <input
                    class="
                      appearance-none
                      block
                      w-full
                      text-gray-700
                      border border-gray-200
                      rounded
                      py-3
                      px-4
                      leading-tight
                      focus:outline-none
                    "
                    type="text"
                    placeholder="*jika lebih dari satu pisahkan dengan tanda koma (,)"
                    v-model="campaign.data.perks"
                    readonly
                  />
                  <small class="text-gray-400"
                    >*silahkan hubungi admin jika ingin mengubahnya</small
                  >
                </div>

                <div class="w-full mb-4 px-3">
                  <label
                    class="
                      block
                      uppercase
                      tracking-wide
                      mb-2
                      text-gray-700 text-xs
                      font-bold
                    "
                  >
                    Deskripsi Komoditas
                  </label>
                  <textarea
                    rows="5"
                    class="
                      appearance-none
                      block
                      w-full
                      bg-gray-200
                      text-gray-700
                      border border-gray-200
                      rounded
                      py-3
                      px-4
                      leading-tight
                      focus:outline-none focus:border-gray-500
                    "
                    type="text"
                    placeholder=""
                    v-model="campaign.data.description_komoditas"
                  ></textarea>
                </div>

                <div class="w-full mb-4 px-3">
                  <label
                    class="
                      block
                      uppercase
                      tracking-wide
                      mb-2
                      text-gray-700 text-xs
                      font-bold
                    "
                  >
                    Deskripsi Prospek
                  </label>
                  <textarea
                    rows="5"
                    class="
                      appearance-none
                      block
                      w-full
                      bg-gray-200
                      text-gray-700
                      border border-gray-200
                      rounded
                      py-3
                      px-4
                      leading-tight
                      focus:outline-none focus:border-gray-500
                    "
                    type="text"
                    placeholder=""
                    v-model="campaign.data.description_prospek"
                  ></textarea>
                </div>

                <div class="w-full mb-4 px-3">
                  <label
                    class="
                      block
                      uppercase
                      tracking-wide
                      text-gray-700 text-xs
                      font-bold
                      mb-2
                    "
                  >
                    Deskripsi Risiko
                  </label>
                  <textarea
                    rows="5"
                    class="
                      appearance-none
                      block
                      w-full
                      bg-gray-200
                      text-gray-700
                      border border-gray-200
                      rounded
                      py-3
                      px-4
                      leading-tight
                      focus:outline-none focus:border-gray-500
                    "
                    type="text"
                    placeholder=""
                    v-model="campaign.data.description_risiko"
                  ></textarea>
                </div>

                <div class="w-full mb-4 px-3">
                  <label
                    class="
                      block
                      uppercase
                      tracking-wide
                      text-gray-700 text-xs
                      font-bold
                      mb-2
                    "
                  >
                    Deskripsi Kelompok Tani
                  </label>
                  <textarea
                    rows="5"
                    class="
                      appearance-none
                      block
                      w-full
                      bg-gray-200
                      text-gray-700
                      border border-gray-200
                      rounded
                      py-3
                      px-4
                      leading-tight
                      focus:outline-none focus:border-gray-500
                    "
                    type="text"
                    placeholder=""
                    v-model="campaign.data.description_kelompok_tani"
                  ></textarea>
                </div>
              </div>
            </form>
          </div>
        </div>
      </div>
    </section>
    <Footer />
  </div>
</template>
<script>
export default {
  middleware: "auth",
  async asyncData({ $axios, params }) {
    const campaign = await $axios.$get("/api/v1/projek/" + params.id);
    return { campaign };
  },

  methods: {
    async save() {
      try {
        let response = await this.$axios.$put(
          "/api/v1/projek/" + this.$route.params.id,
          {
            name: this.campaign.data.name,
            short_description: this.campaign.data.short_description,
            address: this.campaign.data.address,
            description_komoditas: this.campaign.data.description_komoditas,
            description_prospek: this.campaign.data.description_prospek,
            description_risiko: this.campaign.data.description_risiko,
            description_kelompok_tani:
              this.campaign.data.description_kelompok_tani,
            goal_amount: this.campaign.data.goal_amount,
            min_pembayaran: this.campaign.data.min_pembayaran,
            perks: this.campaign.data.perks.join(),
          }
        );
        this.$router.push({
          name: "dashboard-projek-id",
          params: { id: response.data.id },
        });
        console.log(response);
      } catch (err) {
        console.log(err);
      }
    },
    changeImage(url) {
      this.default_image = url;
    },
  },
};
</script>
<style lang="scss"></style>
