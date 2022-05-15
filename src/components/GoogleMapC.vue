<template>
<div class="maps">
    <GoogleMap api-key="AIzaSyCWrEX8F6my1xYIFzbG2i2b_CkmHro6g8U"  :center="center" :zoom="15" class="maps">
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
  setup () {
    const center = { lat: 16.84942, lng: -99.90891 }

    return { center }
  }
})
</script>
