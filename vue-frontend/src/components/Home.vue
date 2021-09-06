<template>
  <div>
    <!-- PART 1: Pass in a "complete" prop here -->
    <Instructions :complete="true" />
    <!-- PART 6: Add a new show -->
    <div>
      <p class="title">Add a new show...</p>
      <input v-model="showName" placeholder="Enter a show name" />
      <button type="button" v-on:click="addShow()">Submit</button>
    </div>
    <!-- PART 4: Modify the Show component to accept all of these props -->
    <Show
      v-for="show in shows"
      :key="show.id"
      :id="show.id"
      :name="show.name"
      :episodes_seen="show.episodes_seen"
    />
  </div>
</template>

<script>
import Instructions from "./Instructions.vue";
import Show from "./Show.vue";

export default {
  components: {
    Instructions,
    Show
  },
  data() {
    return {
      shows: [
        { id: 1, name: "Game of Thrones", episodes_seen: 0 },
        { id: 2, name: "Naruto", episodes_seen: 220 },
        { id: 3, name: "Black Mirror", episodes_seen: 3 }
      ]
    };
  },
  methods: {
    addShow: function() {
      let show = {
        id: this.shows.length + 1,
        name: this.showName,
        episodes_seen: 0
      };
      this.shows.push(show);
    }
  }
};
</script>

<style>
</style>


