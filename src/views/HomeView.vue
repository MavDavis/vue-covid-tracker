<template>
  <main v-if="!loading">
    <Date :date="dataDate" :text="title" />
    <ResultBoxes :stats="status"/>
    <SelectCountry :country="countries" @get-country="getCountry" />
  </main>
  <main class="flex flex-col align-center justify-center text-center" v-else>
    <div class="text-gray-500 text-3xl mt-10 mb-6">Fetching Data..</div>
  </main>
</template>

<script>
import ResultBoxes from "../components/resultBoxes";
import Date from "../components/date";
import SelectCountry from "../components/SelectCountry";
export default {
  name: "HomeView",
  data() {
    return {
      loading: true,
      dataDate: "",
      title: "Global",
      status: {},
      countries: [],
    };
  },
  components: {
    Date,
    SelectCountry,
    ResultBoxes,
  },
  methods: {
    getCountry(country){
      this.status = country
    }
  },
  created() {
    fetch("https://api.covid19api.com/summary")
      .then((response) => response.json())
      .then((result) => {
        this.countries = result.Countries;
        this.dataDate = result.Date;
        this.status = result.Global;
        this.loading = false;
       
      })
      .catch((error) => console.log("error :" + error));
  },
};
</script>
