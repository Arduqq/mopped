<template>
    <div class="BucketList">
        <ul class="BucketListEntries" v-for="bucket in buckets" :key="bucket.id">
                <li v-show="!bucket.done" class="BucketListEntryUndone">{{ bucket.title }}</li><div v-show="!bucket.done" class="BucketListCheck">✔️</div>
                <li v-show="bucket.done" class="BucketListEntryDone">{{ bucket.title }}</li><div v-show="!bucket.done" class="BucketListCheck">✔️</div>
        </ul>
        <div class="BucketListFooter">{{ bucketlistnumber }}</div>
        <p>
            <strong>Progression</strong> - Mopped {{buckets.filter(bucket => {return bucket.done === true}).length}} out of
            {{buckets.filter(bucket => {return bucket.done === false}).length}} buckets!
        </p>
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

    .BucketListEntryDone {
        text-align: right;
        display: block;
        padding: 3%;
        border-right: solid 8px #d5eb34;
        width: 80%;
        cursor: pointer;
        background: linear-gradient(to left, #fcffcc 50%, #404040 50%);
        background-size: 200% 100%;
        background-position: left bottom;
        transition: all .2s ease-out;
    }

    .BucketListEntryUndone {
        display: block;
        padding: 3%;
        border-left: solid 8px #ff6161;
        width: 80%;
        cursor: pointer;
        background: linear-gradient(to right, #fcffcc 50%, #404040 50%);
        background-size: 200% 100%;
        background-position: right bottom;
        transition: all .2s ease-out;
    }

    .BucketListEntryDone:hover {
        background-position: right bottom;
        color: #404040;
    }

    .BucketListEntryUndone:hover {
        background-position: left bottom;
        color: #404040;
    }

    .BucketListEntryUndone:hover + .BucketListCheck{
        animation-name: boing-right;
        animation-duration: 1s;
        animation-delay: .2s;
        animation-fill-mode:forwards;
    }

    .BucketListEntryDone:hover + .BucketListCheck{
        animation-name: boing-left;
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

    @keyframes boing-right {
        20%   {left: 22px; color: #fcffcc;}
        40%  {left: 7px; color: #fcffcc;}
        60%  {left: 17px; color: #fcffcc;}
        80%   {left: 8px; color: #fcffcc;}
        100% {left: 10px; color: #fcffcc;}
    }

    @keyframes boing-left {
        20%   {right: 22px; color: #fcffcc;}
        40%  {right: 7px; color: #fcffcc;}
        60%  {right: 17px; color: #fcffcc;}
        80%   {right: 8px; color: #fcffcc;}
        100% {right: 10px; color: #fcffcc;}
    }
</style>