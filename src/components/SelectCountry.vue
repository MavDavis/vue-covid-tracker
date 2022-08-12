<template>
  <select 
  v-model="selected"
   class="form-select mt-10 block w-full border p-5 rounded mx-3"
   @change="ChangeCountry">
  <option value="0">Select Country</option>
    <option
      v-for="county in country"
      :value="county.ID"
      :key="county.ID"
    >
      {{ county.Country }}
    </option>
  </select>

</template>

<script>
export default {
  data(){
    return{
      selected:0
    }
  },
  props: ["country"],

  methods: {
    ChangeCountry(){
      const Activecountry =this.country.find(county=>county.ID == this.selected) 
      console.log(Activecountry)
      this.$emit('get-country', Activecountry)
    }
  },
};
</script>

<style></style>
