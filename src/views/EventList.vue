<script>
import EventCard from '@/components/EventCard.vue';
import EventService from '@/services/EventService.js'

export default {
  name: 'EventList',
  components: {
    EventCard
  },
  data() {
    return {
      events: {}
    }
  },
  created() {
    EventService.getEvents()
    .then((res) => {
      this.events = res.data;
    })
    .catch((err) => {
      console.log(err);
    })
  }
};

</script>

<template>
  <main>
    <div class="events">
      <h1>Ryan's Events</h1>
      <EventCard v-for="event in events" :key="event.id" :event="event"></EventCard>
    </div>
  </main>
</template>

<style scoped>
 .events {
  display: flex;
  flex-direction: column;
  align-items: center;
 }
</style>
