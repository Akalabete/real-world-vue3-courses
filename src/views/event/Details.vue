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
  <p>{{ props.event.time }} on {{ props.event.date }} @ {{ props.event.location }}</p>
  <p>{{ props.event.description }}</p>
  <p>Theres are {{ props.placeLeft }} places left</p>
</template>
