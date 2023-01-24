<template>
<div class="focus">
    <div class="focusfield">
        <h1 class="head1">My first Vue app</h1>
        <input type="text" ref="inputRef" />
        <button @click="focusInput">Focus</button>
        <button @click="this.showModel = true">Show Modal</button>
    </div>
    <modalView title="Signup for the Giveaway" content="Grap your item for half prize" theme="sales" class="modal" v-show="showModel" @close="this.showModel = false" @open="this.showModel = true">
        <template v-slot:default>
            <h2>Hello world</h2>
        </template>
        <template v-slot:link>
            <a href="">Named slot</a>
        </template>
    </modalView>
</div>
</template>

<script>
import modalView from "./components/modal.vue";
export default {
    name: "App",
    data() {
        return {
            showModel: false,
        };
    },
    methods: {
        focusInput() {
            this.$refs.inputRef.focus();
        },
    },
    components: {
        modalView,
    },
};
</script>

<style>
.focus {
    position: absolute;
    width: 100%;
}

.head1 {
    font-size: 21px;
}

.focusfield {
    display: flex;
    flex-direction: column;
    align-items: center;
}

.focusfield input {
    width: 200px;
    height: 25px;
}

.focusfield button {
    width: 150px;
    height: 30px;
    font-size: 20px;
    margin-top: 10px;
}
</style>
