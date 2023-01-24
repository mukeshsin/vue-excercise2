<template>
<div class="container" @click.prevent.capture="$emit('close')">
    <div :class="theme === 'sale' ? 'red' : 'containerWrap'" @click.prevent="$emit('open')">
        <h1 class="containerTitle">{{ title }}</h1>
        <h3 class="containerContent">{{ content }}</h3>
        <slot></slot>
        <div class="links">
            <slot name="link"></slot>
        </div>
    </div>
</div>
</template>

<script>
export default {
    name: "modalView",

    props: ["title", "content", "theme"],
    emits: ["close", "open"],
    methods: {},
};
</script>

<style scoped>
.container {
    width: 100%;
    height: 100vh;
    background-color: grey;
    position: fixed;
    margin: 0;
    top: 0;
}

.red {
    width: 500px;
    height: 250px;
    border-radius: 25px;
    position: absolute;
    background-color: red;
    top: 20%;
    text-align: center;
    color: white;
    left: 35%;
}

.containerWrap {
    width: 500px;
    height: 350px;
    border-radius: 25px;
    position: absolute;
    background-color: white;
    top: 20%;
    text-align: center;
    color: green;
    left: 35%;
}

.containerTitle {
    margin-top: 10%;
    font-size: 40px;
}

.containerContent {
    margin-top: 10%;
    font-size: 25px;
}

.links {
    font-size: 20px;
    background-color: lightskyblue;
    width: 120px;
    margin-left: 35%;
    height: 35px;
    border-radius: 10px;
    border: solid 2px black;
    padding: 8px;
}
</style>
