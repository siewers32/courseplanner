<template>
    <div>Hello {{ firstName }}</div>
    <p>{{ checkLoggedIn() }}</p>
      <h1 v-if="checkLoggedIn()">Yo</h1>
      <ul v-for="course in courses">
        <li>
          {{ course }}
        </li>
      </ul>

      <button @click="count++">{{ count }}</button>
</template>

<script setup>
    import {ref} from 'vue'
    const firstName = ref('Jan Jaap')
    const app = createApp({
    data() {
            return {
                count: 0,
                courses: [
                    {
                        "id": "532",
                        "name": "HTML",
                        "scrum-points": "24",
                      },
                      {
                        "id": "533",
                        "name": "PHP",
                        "scrum-points": "24",
                      },                  {
                        "id": "534",
                        "name": "Laravel",
                        "scrum-points": "24",
                      },
                ],
            }
        },
    methods: {
       checkLoggedIn() {
            localStorage.setItem('test', 'test')
            return localStorage.getItem('test')
       },
    },
    beforeUpdate() {
            fetch("https://hplussport.com/api/products/order/price")
                .then(response => response.json())
                .then(data => {
                    this.courses = data;
                    return data;
                })
    }
    })
</script>