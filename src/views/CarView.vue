<script setup>

 import {useRoute, useRouter, RouterView} from "vue-router"
 import cars from "../data/cars.json"
 
 
    const route =useRoute()
    const router =useRouter()

    const carId = parseInt(route.params.id)

    const car = cars.find(c => c.id === carId);


    
</script>

<template>
    <div v-if="car">
        <h1>CAR VIEW</h1>
        <p>{{ car.name }}</p>
        <p>{{ car.price }}</p>
        <p>{{ car.year}}</p>
        <button @click="router.push(`/cars/${carId}/contact`)" >Click for Contact</button>
        <RouterView />  
    </div>

    <div v-else>
        <h1>Car No Found..</h1>
        <a href="/">GO BACK </a>
    </div>
</template>