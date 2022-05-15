<template>
  <div>
    <GoogleMap
      api-key="AIzaSyCWrEX8F6my1xYIFzbG2i2b_CkmHro6g8U"
      style="width: 100%"
      :center="center"
      :zoom="15"
    >
      <Marker :options="{ position: center }" />
    </GoogleMap>
  </div>
</template>

<script>
import { defineComponent } from 'vue'
import { GoogleMap, Marker } from 'vue3-google-map'

export default defineComponent({
  name: 'GoogleMaping',
  components: { GoogleMap, Marker },
  setup () {
    const center = { lat: 40.689247, lng: -74.044502 }

    return { center }
  }
})
</script>
