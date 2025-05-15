<script setup>
var name = "Muzammil"

var links = ["home", "about", "contact", "profile"]


</script>

<template>
    <div class="w-full h-screen flex flex-col gap-1 justify-center items-center">

        <h1>Welcome back {{ name }}</h1>
        <p v-if="age < 18">he cannot vote</p>
        <p v-if="age >= 18">he can vote</p>

        <p v-for="(x, i) in links">{{ i + ":" + x }}</p>

    </div>

</template>
