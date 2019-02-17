<template>
    <div class="hello">
        <p v-if="loading">Loading...</p>

        <ul>
            <li v-for="(item, key) in results" v-bind:key="key">
                <Item :item="item" />
            </li>
        </ul>
    </div>
</template>

<script>
    import axios from 'axios';
    import Item from './Item';

    export default {
        name: 'List',
        components: {
            Item
        },
        props: {},
        data: () => {
            return {
                results: [],
                loading: false
            }
        },
        mounted() {
            this.loading = true;
            axios.get(`https://randomuser.me/api/?results=20`)
                .then((res) => {
                    this.loading = false;
                    this.results = res.data.results;
                })
                .catch(() => this.loading = false);
        }
    }
</script>

<style scoped>
    ul {
        margin: 0;
        padding: 0;
        text-align: left;
    }
</style>
