<template>
    <div class="Header">
        <h2>This is the iconic {{ customList ? customList : 'Bucketlist' }} of</h2>
        <h1>{{ owner }}</h1>
        <h2>{{ customDescription ? customDescription : 'Truly iconic.' }}</h2>
    </div>
</template>

<script>
    export default {
        name: "Header",
        props: {
            owner: String,
            customList: String,
            customDescription: String
        }
    }
</script>

<style scoped>
    h1 {
        text-align: center;
        margin: 20px;
        font-size: 7vw;
        font-weight: 700;
        color: #2b2b2b;
        -webkit-text-stroke: 10px #ff6161;
        paint-order: stroke fill;
        text-transform: uppercase;
    }

    h2 {
        text-transform: uppercase;
        text-align: center;
        font-weight: 700;
        display: block;
        font-size: 3vw;
    }
</style>