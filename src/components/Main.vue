<template>
    <div class="container">
        <h1>Film</h1>
        <ul>
            <Card
            v-for="(card, index) in movieCards"
            :key="index"
            :card="card" 
            />
        </ul>

         <h1>Series</h1>
        <ul>
            <TvTemplate 
            v-for="(item, index) in movieCards"
            :key="index"
            :item="item" 
            />
        </ul>
    </div>
</template>

<script>
import Card from './Card.vue'
import TvTemplate from './TvTemplate.vue'
export default {
    name: 'Main',
    props: ['movieCards'],
    components:  {
        Card,
        TvTemplate
    },
    
}
</script>

<style scoped lang="scss">

</style>