<template>
<div class="focus">
<h1 class="head1">My first Vue app</h1>
    <input ref="inputRef" />
    <button @click="focusInput">focus</button>
</div>
</template>

<script>
export default {
    methods: {
        focusInput() {
            this.$refs.inputRef.focus();
        },
    },
};
</script>

<style>

.focus{

text-align:center;
margin-top:60px;


}
.head1{
  font-size:21px;

}
</style>
