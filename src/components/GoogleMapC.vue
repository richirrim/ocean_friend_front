<template>
<div class="maps">
    <GoogleMap api-key="apiKey"  :center="center" :zoom="15" class="maps">
    <Marker :options="{ position: center }" />
  </GoogleMap>
</div>

</template>
<style scoped>
 .maps{
   display: contents;
   position: absolute;
 }
</style>
<script>
import { defineComponent } from 'vue'
import { GoogleMap, Marker } from 'vue3-google-map'

export default defineComponent({
  name: 'GoogleMaping',
  components: { GoogleMap, Marker },
  data: {
    apiKey= process.env.API_KEY_MAPS
  }
  setup () {
    const center = { lat: 16.84942, lng: -99.90891 }

    return { center }
  }
})
</script>
