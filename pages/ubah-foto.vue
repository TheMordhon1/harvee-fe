<template lang="">
  <div class="container mx-auto h-screen flex justify-center items-center">
    <div class="w-full lg:w-1/3 px-10 lg:px-0">
      <div class="flex justify-center items-center mx-auto mb-4 w-40">
        <div class="flex justify-center items-center mx-auto mb-4 w-40">
          <div class="relative">
            <div class="cursor-pointer" @click="$refs.file.click()">
              <img
                :src="url"
                alt=""
                class="rounded-full border-white border-4 h-40 w-40"
              />
              <img
                src="/icon-avatar-change.svg"
                alt=""
                class="absolute right-0 bottom-0 pb-2"
              />
            </div>
            <input
              type="file"
              ref="file"
              style="display: none"
              accept="images/*"
              @change="onFileChange"
            />
          </div>
        </div>
      </div>
      <!-- <h2 class="font-normal mb-3 text-3xl text-white text-center">
            Halo, Ardi
          </h2> -->
      <h2 class="font-normal mb-3 text-3xl text-white text-center">
        Halo, {{ this.$store.state.auth.user.name }}
      </h2>
      <p class="text-white text-center font-light">
        Silahkan, unggah foto terbaik mu !
      </p>
      <div class="mb-4 mt-6">
        <div class="mb-3">
          <button
            :disabled="selectedFiles == undefined"
            @click="upload"
            :class="
              selectedFiles == undefined ? 'opacity-50 cursor-not-allowed' : ''
            "
            class="
              block
              w-full
              bg-button-rounded
              text-white
              font-semibold
              px-6
              py-4
              text-lg
              rounded-full
            "
          >
            Ubah Foto
          </button>
        </div>
      </div>
      <div>
        <div class="mb-4">
          <button
            @click="$router.push({ path: '/' })"
            class="
              block
              w-full
              btn-redirect
              text-white
              font-light
              px-6
              py-4
              text-lg
            "
          >
            Kembali
          </button>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  layout: "auth",
  data() {
    return {
      url: "/avatar.jpg",
      selectedFiles: undefined,
    };
  },
  methods: {
    onFileChange(e) {
      const file = e.target.files[0];
      this.url = URL.createObjectURL(file);
      this.selectedFiles = this.$refs.file.files;
    },
    async upload(file) {
      let formData = new FormData();

      formData.append("avatar", this.selectedFiles.item(0));

      try {
        let response = await this.$axios.post("/api/v1/avatars", formData, {
          headers: {
            "Content-Type": "multipart/form-data",
          },
        });
        console.log(response);

        this.$router.push({ path: "/ubah-foto-berhasil" });
      } catch (err) {
        console.log(err);
      }
    },
  },
};
</script>
<style scoped></style>
