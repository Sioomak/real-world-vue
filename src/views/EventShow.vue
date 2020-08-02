<template>
  <h1>Showing event #{{ id }}</h1>
</template>
<script>
import EventService from '@/servies/EventSerice.js'
export default {
  props: ['id'],
  data() {
    return {
      event: {}
    }
  },
  created() {
    EventService.getEvent(this.id)
      .then(response => {
        this.event = response.data
      })
      .catch(error => {
        console.log("there's an Errror: " + error)
      })
  }
}
</script>
