<script>
import EventService from '@/services/EventService.js'
export default {
  props: ['id'],
  data() {
    return {
      event: {},
    }
  },
  created() {
    // fetch event by id and set local data
    EventService.getEventById(this.id)
    .then((res) => {
      this.event = res.data;
    })
    .catch((err) => {
      console.log(err);
    })
  }
}
</script>

<template>
  <div>
    <h1>{{ event.title }}</h1>
      <p>{{ event.time }} on {{ event.date }} @ {{ event.location }}</p>
      <p>{{ event.description }}</p>
  </div>
</template>
