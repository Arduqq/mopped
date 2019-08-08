<template>
    <div class="BucketList">
        <h1>You are currently viewing the bucketlist of {{ owner }} ({{ bucketlistnumber }})</h1>
        <p>
            <strong>Progression</strong> - Mopped {{buckets.filter(bucket => {return bucket.done === true}).length}} out of
            {{buckets.filter(bucket => {return bucket.done === false}).length}} buckets!
        </p>
        <ul class="BucketListEntries" v-for="bucket in buckets" :key="bucket.id">
            <li class="BucketListEntry">{{ bucket.title }}</li>
        </ul>
    </div>
</template>

<script>
    export default {
        name: "BucketList",
        props: {
            buckets: Object,
            owner: String,
            bucketlistnumber: Int16Array
        }
    }
</script>

<style scoped>
    .BucketList {
        border: solid black 2px;
        border-radius: 15px;
        padding: 5%;
    }

    .BucketListEntries {
        display: flex;
        flex-direction: row;
        flex-wrap: wrap;
        justify-content: flex-start;
    }

    .BucketListEntry {
        display: block;
    }
</style>