<template>
    <div class="BucketListPrompt">
        <form class="BucketAddForm">
            <input v-model="titleText" placeholder="New Bucketlist Entry" class="EntryInput" type="text"/>
            <button class='EntryButton' v-on:click="sendForm()">Send</button>
        </form>
    </div>
</template>

<script>
  export default {
    name: "BucketListPrompt",
    data() {
      return {
        titleText: ''
      };
    },
    methods: {
      sendForm() {
        if (this.titleText.length > 0) {
          const title = this.titleText;
          this.$emit('create-todo', {
            title,
            id: 999999,
            done: false,
          });
        }
      },
    }
  }
</script>

<style scoped>
    .BucketListPrompt {
        margin-left:auto;
        margin-right:auto;
        margin-bottom: 2%;
        border-radius: 100%;
        width: 5%;
        height: 5%;
        background-color: #ff6161;
        border: solid 10px #ff6161;
        transition: .1s;
        animation-name: drip;
        animation-duration: 1s;
        animation-fill-mode: backwards;
        z-index: -5;
    }

    .BucketListPrompt:after {
        content: "";
        display: block;
        padding-bottom: 100%;
    }

    .BucketListPrompt:hover {
        transition:  .1s;
        border-radius: 0;
        background-color: #404040;


        animation-name: clog;
        animation-duration: .2s;
        animation-fill-mode: forwards;
    }

    .BucketListPrompt:hover .BucketAddForm {
        visibility: visible;
        opacity: 1;
    }

    .BucketAddForm {
        position: absolute;
        width: 100%;
        height: 100%;
        visibility: hidden;
        transition: all .3s linear;
        opacity: 0;
    }

    .EntryInput {
        padding: 15px;
        margin-top: 1%;
        margin-left: -10%;
        margin-right: -10%;
        font-size: 15pt;
        font-family: 'Space Mono', Helvetica, Arial, sans-serif;
        border: none;
        width: 40%;
        color: #fcffcc;
        background-color: #5e5e5e;
    }

    @keyframes clog {
        0% {width: 5%}
        50% {width: 10%}
        100% {width: 20%}
    }

    @keyframes drip {
        0% {width: 20%}
        50% {border-radius: 100%;height: 1px; transform: translate(0px, 150px)}
        100% {width: 5%;}
    }
</style>