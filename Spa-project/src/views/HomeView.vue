<script setup>
    import HeroImage from '../components/HeroImage.vue'
    import SpaOffers from '../components/SpaOffers.vue'
</script>

<template>
    <HeroImage />
    <h1 class="title">{{ message }}</h1>
    <div id="offers">
        <div class="container text-center">
            <div class="row align-items-start">
                <Spa-Offers v-for="spa in spas" :key="spa.id" :offer="spa" />
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                message: 'Recommended For You',
                spas: []
            }
        },
        name: 'HomeView',
        components: { 'spa-offers': SpaOffers },
        mounted() {
            this.fetchData()
        },
        methods: {
            async fetchData() {
                const res = await fetch('spa.json')
                const val = await res.json()
                this.spas = val
                console.log(val)
            }
        }
    }
</script>

<style scoped>
    #offers {
        display: flex;
        justify-content: center;
        margin-top: 10vh;
        margin-bottom: 10vh;
    }

    .title {
        display: flex;
        justify-content: center;
        margin-top: 10px;
    }
</style>
