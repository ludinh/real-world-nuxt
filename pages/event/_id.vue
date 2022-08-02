<template>
  <div class="wrap-content">
    <h1>{{ event.title }}</h1>
  </div>
</template>

<script>
import EventService from "@/services/EventService.js";
export default {
  head() {
    return {
      title: "Event " + this.event.title,
      meta: [
        {
          hid: "description",
          name: "description",
          content:
            "Create page description tells you find all techniques in your " +
            this.event.title,
        },
      ],
    };
  },
  async asyncData({ $axios, error, params }) {
    try {
      const { data } = await EventService.getEvent(params.id);
      return {
        event: data,
      };
    } catch (e) {
      error({
        statusCode: 503,
        message: "Unable to fetch event #" + params.id,
      });
    }
  },
};
</script>
