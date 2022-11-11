<template>
    <div>Hello {{ firstName }}</div>
    <ListComponent :href="test(24)"></ListComponent>
    <ListComponent href="/learningpaths"></ListComponent>
</template>

<script setup>
    import {ref} from 'vue'
    import ListComponent from './ListComponent.vue';
    const firstName = ref('Jan Jaap')
    function test(a) {
        return "/learningpath/" + a + "/courses";
    }
</script>