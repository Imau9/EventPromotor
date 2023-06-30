<template>
  <div class="home">
    <h1>Welcome to Home page </h1>
    <div class="event-container">
      <div class="event-card" v-for="event in events" :key="event.id">
        <img :src="event.image" alt="Event Image" class="event-image">
        <h3 class="event-title">{{ event.title }}</h3>
        <p class="event-description">{{ event.description }}</p>
        
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      events: [
        {
          id: 1,
          title: "Metallica",
          description: "Metallica-Arena Pula",
          image: require("@/assets/metalica.png")
        },
        {
          id: 2,
          title: "Iron Maiden",
          description: "Iron Maiden-Kastel Pula",
          image: require("@/assets/iron_maiden.png")
        },
        // Add more events as needed
      ]
    };
  }
};
</script>


<style scoped>
.home {
  text-align: center;
  background-image: linear-gradient(to bottom right, #333, #222), url("@/assets/background.png");
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
  color: #fff;
  padding: 20px;
}

.event-container {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-wrap: wrap;
}

.event-card {
  margin: 20px;
  padding: 20px;
  width: 300px;
  border: 1px solid #ccc;
  border-radius: 5px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  background-color: rgba(0, 0, 0, 0.8);
}

.event-image {
  width: 100%;
  max-height: 200px;
  object-fit: cover;
  border-radius: 5px;
}

.event-title {
  margin-top: 10px;
  font-size: 20px;
}

.event-description {
  margin-top: 10px;
}

.event-button {
  margin-top: 20px;
  padding: 10px 20px;
  background-color: #007bff;
  color: #fff;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  transition: background-color 0.3s;
}

.event-button:hover {
  background-color: #0056b3;
}
</style>