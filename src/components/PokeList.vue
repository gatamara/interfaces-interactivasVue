<template>
    <h3>Pokemones descubiertos: <span id="count">{{ discoveredCount }}</span> </h3>
    <div>
        <ul>
            <PokeItem v-for="(pokemon, index) in pokemones" :key="index" :pokemon="pokemon" :index="index"
                :correctNames="correctNames" @discover="addToCorrectNames" />
        </ul>
    </div>
</template>

<script setup>
import { onMounted, ref, computed } from 'vue';
import axios from 'axios';
import PokeItem from './PokeItem.vue';

const pokemones = ref([]);
const correctNames = ref(new Set());

onMounted(async () => {
    try {
        const requests = [];
        for (let i = 1; i <= 150; i++) {
            requests.push(axios.get(`https://pokeapi.co/api/v2/pokemon/${i}`));
        }
        const responses = await Promise.all(requests);
        pokemones.value = responses.map(response => response.data);
    } catch (error) {
        console.error('Error al obtener los Pokémon:', error);
    }
});

const addToCorrectNames = (name) => {
    correctNames.value.add(name);
};

const discoveredCount = computed(() => correctNames.value.size);
</script>

<style scoped>
ul {
    list-style-type: none;
    padding: 0;
    display: flex;
    flex-wrap: wrap;
}

li {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    padding: 32px;
}

h3 {
    text-align: center;
}

#count {
    color: rgb(252, 194, 47);
}
</style>