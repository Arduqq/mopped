<template>
  <div id="app">
      <Header v-bind:owner="owner"
              v-bind:customList="customList"/>

      <BucketListPrompt v-on:add-todo="addTodo"/>

      <BucketList v-bind:buckets="buckets"
                  v-bind:owner="owner"
                  v-bind:bucketlistnumber="bucketlistnumber"
                  v-bind:customDescription="customDescription"/>

  </div>
</template>

<script>
import BucketList from './components/BucketList.vue';
import BucketListPrompt from './components/BucketListPrompt.vue'
import Header from "@/components/Header";

export default {
  name: 'app',
  components: {
    Header,
    BucketList,
    BucketListPrompt
  },
  data() {
    return {
      owner: "Arduqq",
      customList: '',
      customDescription: 'What a snack',
      bucketlistnumber: 1863817,
      buckets: [{
        title: 'Zu einem Rammstein-Konzert gehen',
        id: 183628,
        done: true,
      }, {
        title: 'Manila Luzon treffen',
        id: 292846,
        done: false,
      }, {
        title: 'Den Jakobsweg laufen',
        id: 192555,
        done: false,
      },{
        title: 'In New York an die richtig falschen Leute geraten',
        id: 192236,
        done: false,
      },{
        title: 'Ein Videospiel veröffentlichen',
        id: 176546,
        done: false,
      },{
        title: 'In Drag eine Performance abliefern',
        id: 197472,
        done: false,
      }],
    };
  },
  methods: {
    addTodo(title) {
      this.buckets.push({
        title,
        done: false,
      });
    },
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css?family=Space+Mono&display=swap');

    #app {
        font-family: 'Space Mono', Helvetica, Arial, sans-serif;
        -webkit-font-smoothing: antialiased;
        -moz-osx-font-smoothing: grayscale;
        color: #fcffcc;
}
    html {
        overflow-x: hidden;
        background-color: #2b2b2b;
    }
</style>
