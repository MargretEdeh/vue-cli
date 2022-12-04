<template>
    <div class="event">
      <div class="each" :key="event.id" v-for="event in events">
        <h1 class="h1">
          {{ event.social }}
          <i @click="onDelete(event.id)" class="fas fa-trash"></i>
        </h1>
        <p>{{ event.date }}</p>
        <p class="ptag">
          Dress color:
          <span
            ><div :style="{ background: event.color }" class="box"></div
          ></span>
        </p>
      </div>
    </div>

</template>

<script>
export default {
  name: "EventPart",
  
  props: {
    events: Array,
  },
  methods: {
    onDelete(id) {
      this.$emit("delete-event", id);
    },
  },
};
</script>

<style scoped>
.fas {
  color: red;
  font-size: 18px;
  cursor: pointer;
  margin-right: 10px;
}
.fas:hover {
  font-size: 25px;
  margin-right: 15px;
}
.ptag {
  display: flex;
}
.h1 {
  display: flex;
  justify-content: space-between;
  font-style: italic;
}

.event {
  margin-top: 3em;
  flex-direction: column;
  color: #181818;
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  width: 50%;
}
.each {
  margin: 10px;
  padding: 20px 10px;
  border-radius: 10px;
  width: 70%;
  background-color: cyan;
  align-items: flex-start;
  justify-items: flex-start;
  text-align: start;
}
.each:hover {
  background-color: rgb(12, 160, 160);
}
.box {
  width: 20px;
  height: 20px;
  margin-left: 10px;
  margin-top: 2px;
  border-radius: 50%;
}
</style>
