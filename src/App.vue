<template>
  <div class="min-h-screen bg-gray-100">
    <div class="container  mx-auto">
      <div class="bg-white p-4 shadow-lg rounded">
        <div class="flex -mx-4 items-center mb-6">

          <div class="flex-1 px-4">
            <select class="quran-input" name="" id="">
              <option value="">Select Sura</option>
              <option v-for="(sura, key) in suras" value="">{{ key+ 1 }} {{ sura.name }} - {{ sura.englishName }}
              </option>
            </select>
          </div>

          <div class="flex-1 px-4 text-center">
            <h3 class="font-bold mb-1 text-lg">Al-Baqrah</h3>
            <p>The Cow</p>
          </div>

          <div class="flex-1 px-4">
            <select class="quran-input" name="" id="">
              <option value="">Select Sura</option>
            </select>
          </div>

        </div>

        <div class="">
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Autem, animi minus quisquam voluptas cum excepturi
          cumque repellendus ab, consectetur eum voluptatem dolor pariatur voluptatibus optio labore! Modi
          necessitatibus tempora iure!
        </div>

      </div>
    </div>
  </div>
</template>


<script>
import axios from "axios"

export default {
  name: 'App',

  data() {
    return {
      suras: []
    }
  },

  mounted() {
    axios.get("http://api.alquran.cloud/v1/surah")
      .then(response => {
        this.suras = response.data.data
        console.log(response.data);
        // console.log(response.data.data[0].name);
      })
  }
}

</script>