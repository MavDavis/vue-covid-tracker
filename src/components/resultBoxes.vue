<template>
  <div class="grid md:grid-cols-2 gap-4">
    <div class="shadow-md bg-blue-100 p-10 text-center rounded">
        <h3 class="text-3xl text-blue-900 font-bold mb-4">
            Cases
        </h3>
        <div class="text-2xl mb-4">
            <span class="font-bold">New:</span>
            {{cnew}}
             
        </div>
         <div class="text-2xl mb-4">
           <span class="font-bold">Total:</span>
             {{ctotal}}
             
        </div>
    </div>
       <div class="shadow-md bg-blue-100 p-10 text-center rounded">
        <h3 class="text-3xl text-blue-900 font-bold mb-4">
            Deaths
        </h3>
        <div class="text-2xl mb-4">
            <span class="font-bold">New:</span>
            {{dnew}}
             
        </div>
         <div class="text-2xl mb-4">
           <span class="font-bold">Total:</span>
             {{dtotal}}
             
        </div>
    </div>
  </div>
</template>

<script>
export default {
 name:'ResultBoxes',
 props:['stats'],
 method:{
   
    },
    computed:{
        dnew(){
return this.stats.NewDeaths.toLocaleString('en-US')
        },
          dtotal(){
return this.stats.TotalDeaths.toLocaleString('en-US')
        },
          cnew(){
return this.stats.NewConfirmed.toLocaleString('en-US')
        },
          ctotal(){
return this.stats.TotalConfirmed.toLocaleString('en-US')
        },
    }
 }
</script>

<style>

</style>