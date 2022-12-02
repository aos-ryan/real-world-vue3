<script>
import EventCard from '@/components/EventCard.vue'

export default {
  name: 'HomeView',
  components: {
    EventCard
  },
  data() {
    return {
      events: [
        {
        id: 12345,
        category: 'meeting',
        title: 'Breakdown with Client',
        description: 'Meeting with client to breakdown completed project',
        location: 'virtual',
        date: 'December 15, 2022',
        time: '13:00',
        organizer: 'Ryan Kidd'
      },
        {
        id: 12346,
        category: 'social',
        title: 'Lunch with Client',
        description: 'Lunch with client',
        location: 'Tobys',
        date: 'December 18, 2022',
        time: '13:00',
        organizer: 'Ryan Kidd'
      },
        {
        id: 12347,
        category: 'appointment',
        title: 'Dentist Appointment',
        description: 'Annual Checkup',
        location: 'Dr Bastien',
        date: 'December 25, 2022',
        time: '16:30',
        organizer: 'Ryan Kidd'
      },
    ]
    }
  }
}
</script>

<template>
  <main>
    <div class="events">
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
