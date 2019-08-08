<template>
    <div class="BucketList">
        <p>
            <strong>Progression</strong> - Mopped {{buckets.filter(bucket => {return bucket.done === true}).length}} out of
            {{buckets.filter(bucket => {return bucket.done === false}).length}} buckets!
        </p>
        <ul class="BucketListEntries" v-for="bucket in buckets" :key="bucket.id">
            <li class="BucketListEntry">{{ bucket.title }}</li><div class="BucketListCheck">✔️</div>
        </ul>
        <div class="BucketListFooter">{{ bucketlistnumber }}</div>
    </div>
</template>

<script>
    export default {
        name: "BucketList",
        props: {
            buckets: Array,
            owner: String,
            bucketlistnumber: Int8Array
        }
    }
</script>

<style scoped>
    .BucketList {
        border: solid white 10px;
        padding: 5%;
        margin: auto;
        width: 60%;
        background-color: #404040;
    }

    .BucketListEntries {
        font-size: 2vw;
        display: flex;
        flex-direction: row;
        flex-wrap: wrap;
        justify-content: flex-start;
    }

    .BucketListEntry {
        display: block;
        padding: 3%;
        border-left: solid 8px #fcffcc;
        width: 80%;
        cursor: pointer;
        background: linear-gradient(to right, #fcffcc 50%, #404040 50%);
        background-size: 200% 100%;
        background-position: right bottom;
        transition: all .2s ease-out;
    }

    .BucketListEntry:hover {
        background-position: left bottom;
        color: #404040;
    }

    .BucketListEntry:hover + .BucketListCheck{
        animation-name: boing;
        animation-duration: 1s;
        animation-delay: .2s;
        animation-fill-mode:forwards;
    }


    .BucketListFooter {
        font-size: 1vw;
    }

    .BucketListCheck {
        color: #404040;
        position: relative;
        transition: all .3s ease-out;
        left: 10px;
        display: block;
        font-size: 40pt;
        margin-top: auto;
        margin-bottom: auto;
    }

    @keyframes boing {
        20%   {left: 22px; color: #fcffcc;}
        40%  {left: 7px; color: #fcffcc;}
        60%  {left: 17px; color: #fcffcc;}
        80%   {left: 8px; color: #fcffcc;}
        100% {left: 10px; color: #fcffcc;}
    }
</style>