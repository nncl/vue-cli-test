<template>
    <div class="dd-m-item">
        <h1>{{ item.name.first }}</h1>
        <p>{{ item.email }}</p>
    </div>
</template>

<script>
    export default {
        name: 'Item',
        props: {
            item: Object
        }
    }
</script>

<style scoped>
    .dd-m-item {
        margin: 20px 0;
    }

    .dd-m-item h1,
    .dd-m-item p {
        margin: 0;
    }
</style>
