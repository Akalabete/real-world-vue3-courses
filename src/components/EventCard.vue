<script setup>


const props = defineProps({
  event: {
    type: Object,
    required: true,
  },
  placeLeft: {
    type: Number,
    required: true,
  }
});


</script>

<template>
  <router-link
    class="event-link"
    :to="{ name: 'EventDetails', params: { id: props.event.id } }"
  >
    <div class="event-card">
      <h2>{{ props.event.title }}</h2>
      <span>@{{ props.event.time }} on {{ props.event.date }}</span>
      <p>Places left : {{ props.placeLeft  }}</p>
    </div>
  </router-link>
</template>

<style scoped>
.event-card {
  padding: 20px;
  width: 250px;
  cursor: pointer;
  border: 1px solid #39495c;
  margin-bottom: 18px;
}

.event-card:hover {
  transform: scale(1.01);
  box-shadow: 0 3px 12px 0 rgba(0, 0, 0, 0.2);
}

.event-link {
  color: #2c3e50;
  text-decoration: none;
}
</style>
