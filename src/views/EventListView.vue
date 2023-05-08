<script setup>
import { ref, onMounted } from 'vue'
import EventCard from '@/components/EventCard.vue'
import EventService from '@/services/EventService.js'

const events = ref(null)

onMounted(() => {
  EventService.getEvents()
    .then((response) => {
      events.value = response.data
    })
    .catch((error) => {
      console.log(error)
    })
})
</script>

<template>
  <h1>Voy A Cojer Telas</h1>
 <!-- <div class="events">
    <EventCard v-for="event in events" :key="event.id" :event="event" />
  </div>-->
  <h1>MONKEY</h1>
  <!--<img class="myPicture" src="./assets/pat.JPG" alt="SI ASI VA SER" width="300" height="400">-->
</template>

<style scoped>
.events {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.myPicture {
  border-style: solid;
  border-width: 2;
  border-color: yellow;
}
</style>
