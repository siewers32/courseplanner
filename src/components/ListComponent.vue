<template>
    <ul class="listbox" >
        <li class="boxitem" v-for="course in courses">{{ course.id }} {{ course.name }} {{ href }}</li>
    </ul>
</template>

<script setup>
import {ref} from 'vue'
defineProps({
    href: String
})
const courses = ref([])

</script>

<style>
ul.listbox {
    display:flex;
    width:200px;
    flex-direction: column;
    border: 1px black solid;
    border-radius: 8px;
    padding:10px;
    padding-bottom: 0px;
    margin:5px;
}

li.boxitem {
    border: 1px black solid;
    border-radius: 8px;
    list-style: none;
    padding:10px;
    margin-bottom:10px;
}</style>