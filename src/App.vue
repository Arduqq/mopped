<template>
  <div id="app">
      <Header v-bind:owner="owner"
              v-bind:customList="customList"/>

      <BucketList v-bind:buckets="buckets"
                  v-bind:owner="owner"
                  v-bind:bucketlistnumber="bucketlistnumber"
                  v-bind:customDescription="customDescription"/>
  </div>
</template>

<script>
import BucketList from './components/BucketList.vue'
import Header from "@/components/Header";

export default {
  name: 'app',
  components: {
    Header,
    BucketList
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
        id: 192846,
        done: false,
      }, {
        title: 'Den Jakobsweg laufen',
        id: 192846,
        done: false,
      },{
        title: 'In New York an die richtig falschen Leute geraten',
        id: 192846,
        done: false,
      },{
        title: 'Ein Videospiel veröffentlichen',
        id: 192846,
        done: false,
      },{
        title: 'In Drag eine Performance abliefern',
        id: 197472,
        done: false,
      }],
    };
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

        background-color: #2b2b2b;
    }
</style>
