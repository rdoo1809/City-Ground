<script setup>
const props = defineProps({
  day: {
    type: String,
    required: true
  },
  month: {
    type: String,
    required: true
  },
  title: {
    type: String,
    required: true
  },
  description: {
    type: String,
    required: true
  },
  link: {
    type: String,
    required: false
  }
});
</script>

<template>
  <div class="date-card">
    <div class="date-box">
      <span class="date-number">{{ day }}</span>
      <span class="date-month">{{ month }}</span>
    </div>

    <div class="date-info">
      <h3 class="description">{{ title }}</h3>
      <p class="sub-description">{{ description }}</p>
      <a v-if="link" target="_blank" :href="link" class="event-link">More Info Here</a>
    </div>

  </div>
</template>

<style scoped>
.date-card {
  width: 50%;
  display: flex;
  border: 1px solid #ccc;
  border-radius: 8px;
  padding: 12px;
  margin: 6px 0;
  background-color: #f9f9f9;
  box-shadow: 0 4px 6px rgba(255, 255, 255, 0.3), 0 1px 3px rgba(255, 255, 255, 0.2);
}

.date-box {
  width: 150px;
  text-align: center;
  align-content: center;
  background-color: rgb(0, 197, 255);
  color: white;
  padding: 20px;
  border-radius: 8px;
  margin-right: 15px;
}

.date-number {
  font-size: 3rem;
  font-weight: bold;
}

.date-month {
  font-size: 1.2rem;
}

.date-info {
  display: flex;
  flex-direction: column;
  flex-grow: 1;
  text-align: center;
}

.description {
  font-family: "Oswald", sans-serif;
  font-size: 1.5rem;
  font-weight: bold;
  margin: 0;
  color: #213547
}

.sub-description {
  color: #666;
}

.event-link {
  color: rgb(0, 197, 255);
  font-weight: bold;
}

.event-link:hover {
  text-decoration: underline;
}

@media (max-width: 500px) {
  .date-card {
    flex-direction: column;
    align-items: center;
  }

  .date-box {
    margin-right: 0;
  }
}

</style>