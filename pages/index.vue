<template>
  <div class="container">
    <div class="wrap-content">
      <h1>Index Events</h1>
    <EventCard
      v-for="(event, index) in events"
      :key="index"
      :event="event"
      :data-index="index"
    />
    </div>
  </div>
</template>

<script>
import EventCard from "@/components/EventCard.vue";
import { mapState } from "vuex";

export default {
  head() {
    return {
      title: "Events Listing",
      meta: [
        {
          hid: "description",
          name: "description",
          content:
            "Create page description tells you find all techniques in your computer",
        },
      ],
    };
  },

  async fetch({ store, error }) {
    try {
      await store.dispatch("events/fetchEvents");
    } catch (e) {
      error({
        statusCode: 503,
        message: "Unable to fetch events at this time. Please try again",
      });
    }
  },
  components: { EventCard },
  computed: mapState({
    events: (state) => state.events.events,
  }),
};
</script>

<style>
html,
body {
  color: #444;
  border: none;
}
.container {
  position: relative;
  display: block;
  width: 100%;
  height: auto;
  border: none;
}
.wrap-content {
  position: relative;
  display: block;
  width: min(1100px, 90vw);
  margin: 40px auto;
}
a {
  position: relative;
  text-decoration: none;
  color: #444;
}
</style>
