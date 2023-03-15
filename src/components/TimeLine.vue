<script setup>
import Card from './Card.vue';
import Container from './Container.vue';
const data = [
    {
        id: 1,
        username: 'xonyis',
        url: 'https://www.nautiljon.com/images/galerie/10/54/cowboy_bebop_854045.jpg',
        caption: ''
    },
    {
        id: 2,
        username: 'xonyis',
        url: 'https://leclaireur.fnac.com/wp-content/uploads/2022/06/trigun-1256x826.jpeg',
        caption: 'hello guys'
    }
]

</script>
<template>
    <Container>
        <div class="timeline-container">
            <Card v-for="post in data" :key="post.id" :post="post"/>
        </div>
    </Container>
</template>

<style scoped>
.timeline-container {
    display: flex;
    flex-flow: column wrap;
    align-items: center;
    padding: 20px 0px;
}
</style>