<template>
  <div class="flex justify-center text-4xl font-extrabold p-3">
    <h1>Find Your IP</h1>
  </div>

  <div>
    <form class="flex flex-col space-y-2 w-1/2 mx-auto" @submit.prevent="handleSubmit">
      <label for="ip" class="text-sm font-medium text-gray-700">Your IP:</label>
      <div class="flex items-center">
        <input v-model="ip" type="text" id="ip" name="ip" required
          class="w-full px-3 py-2 border border-gray-300 rounded-md focus:outline-none focus:ring-1 focus:ring-blue-500" />
        <button type="submit"
          class="ml-2 py-2 px-3 bg-blue-500 text-white font-medium rounded-md hover:bg-blue-700 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-white">
          Submit
        </button>
      </div>
      <button type="button" @click="fetchApi"
        class="mt-2 py-2 px-3 bg-blue-500 text-white font-medium rounded-md hover:bg-green-700 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-white">
        Find
      </button>
    </form>
  </div>

  <div>
    <div class="container flex justify-center flex-col-1 mx-auto px-4 py-8">
      <div v-if="loading" class="text-center text-xl font-bold">Loading...</div>
      <div v-else>
        <div v-if="apiResponse" class="flex flex-col space-y-4">
          <div class="text-xl font-bold">
            IP Address: <span class="text-blue-500">{{ apiResponse.query }}</span>
          </div>
          <div>Country Code: <span class="font-medium">{{ apiResponse.countryCode }}</span></div>
          <div>Country Name: <span class="font-medium">{{ apiResponse.country }}</span></div>
          <div>City: <span class="font-medium">{{ apiResponse.city }}</span></div>
          <div>Latitude: <span class="font-medium">{{ apiResponse.lat }}</span></div>
          <div>Longitude: <span class="font-medium">{{ apiResponse.lon }}</span></div>
        </div>
        <div v-if="apiResponse" class="flex flex-col space-y-2 mt-4">
          <div class="text-xl font-bold">Connection</div>
          <div>ASN: <span class="font-medium">{{ apiResponse.as }}</span></div>
          <div>Organization: <span class="font-medium">{{ apiResponse.org }}</span></div>
          <div>ISP: <span class="font-medium">{{ apiResponse.isp }}</span></div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      ip: "",
      apiResponse: null,
      error: "",
      loading: false,
    };
  },
  methods: {
    handleSubmit(event) {
      console.log("Form submitted:", this.ip, event);
      event.target.reset();
    },
    async fetchApi() {
      this.loading = true;
      this.apiResponse = null;
      this.error = "";
      const url = `http://ip-api.com/json/${this.ip}`;
      try {
        const response = await fetch(url);
        if (!response.ok) {
          throw new Error(`HTTP error! status: ${response.status}`);
        }
        const data = await response.json();
        console.log("API data:", data);
        this.apiResponse = data;
        this.ip = data.query;
      } catch (error) {
        this.error = error;
        console.error("Error fetching API:", error);
      } finally {
        this.loading = false;
      }
    },
  },
};
</script>
