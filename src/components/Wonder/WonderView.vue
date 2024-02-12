<template>
    <div class="container mt-4">
        <div class="row">
            <div class="col-md-3 mb-5 justify-content-md-start" v-for="item in allVietnam" :key="item.id">
                <div class="card shadow p-0">
                    <img :src="item.imageUrl" class="card-img-top" alt="Vietnam">
                    <div class="card-body">
                        <h5 class="card-title">{{ item.name }}</h5>
                        <p class="card-text">Location - {{ item.location }}</p>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script setup>
import axios from 'axios'
import { onMounted,ref } from 'vue';

const allVietnam = ref([]);

onMounted(() => {
    axios.get(`https://server-json-774h.onrender.com/Vietnam`)
        .then((response) => {
            // console.log(response.data)
            allVietnam.value = response.data
        })
})

</script>

<style lang="scss" scoped></style>