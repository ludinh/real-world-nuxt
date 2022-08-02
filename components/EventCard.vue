<template>
  <nuxt-link :to="'/event/' + event.id" class="event-link">
    <div class="-shadow">
      <span class="eyebrow">
        @{{ event.time}} on {{parsedDate}}
      </span>
      <h4 class="title">
        {{ event.title}}
      </h4>
      <span>
        {{event.attendees.length}} attending
      </span>
    </div>
  </nuxt-link>
</template>

<script>
export default {
  name: "EventCard",
  props: {
    event: Object,
  },
  computed: {
    parsedDate() {
      const eventDate = new Date(this.event.date);
      return eventDate.toDateString();
    },
  },
};
</script>

<style scoped>
div {
  padding: 20px;
  margin-bottom: 25px;
  transition: all 0.2s ease;
  cursor: pointer;
  border: 1px solid rgba(0, 0, 0, 0.1);
  margin: 30px auto;
}
div:hover {
  transform: scale(1.01);
  box-shadow: 0 3px 12px 0 rgba(0, 0, 0, 0.1), 0 1px 15px 0 rgba(0, 0, 0, 0.1);
}
.title {
  position: relative;
  display: block;
  text-align: left;
  font-size: 40px;
  font-weight: 700;
  color: #42b883;
  margin: 20px 0;
}
.event-link {
  position: relative;
  display: block;
  width: 500px;
  margin:auto;
}
</style>
