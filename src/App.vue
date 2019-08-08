<template>
  <div id="app">
    <BucketList v-bind:buckets="buckets" v-bind:owner="owner" v-bind:bucketlistnumber="bucketlistnumber"/>
  </div>
</template>

<script>
import BucketList from './components/BucketList.vue'

export default {
  name: 'app',
  components: {
    BucketList
  },
  data() {
    return {
      owner: "Arduqq",
      bucketlistnumber: '1863817',
      buckets: [{
        title: 'Zu einem Rammstein-Konzert gehen',
        id: 183628,
        done: true,
      }, {
        title: 'Manila Luzon treffen',
        id: 192846,
        done: false,
      }, {
        title: 'In Drag eine Performance abliefern',
        id: 197472,
        done: false,
      }],
    };
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}
</style>
