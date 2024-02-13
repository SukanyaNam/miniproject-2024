<template>
    <div class="container mt-4 ">
        <div class="row">

                            <div id="carouselExampleCaptions" class="carousel slide mb-5">
                            <div class="carousel-indicators ">
                                <button type="button" data-bs-target="#carouselExampleCaptions" data-bs-slide-to="0" class="active" aria-current="true" aria-label="Slide 1"></button>
                                <button type="button" data-bs-target="#carouselExampleCaptions" data-bs-slide-to="1" aria-label="Slide 2"></button>
                                <button type="button" data-bs-target="#carouselExampleCaptions" data-bs-slide-to="2" aria-label="Slide 3"></button>
                            </div>
                            <div class="carousel-inner">
                                <div class="carousel-item active">
                                <img src="https://cdn.pixabay.com/photo/2022/10/07/09/06/bridge-7504605_1280.jpg" class="d-block w-100 h-20" alt="..." height="650">
                                <div class="carousel-caption d-none d-md-block">
                                    <h5>Saigon Bridge</h5>
                                    <p>Hanoi, the city Filled with the scent of art and culture history.</p>
                                </div>
                                </div>
                                <div class="carousel-item">
                                    <img src="https://cdn.pixabay.com/photo/2018/01/04/07/59/salt-3060092_960_720.jpg" class="d-block w-100 h-20" alt="..." height="650">
                                    <div class="carousel-caption d-none d-md-block">
                                    <h5>Salt Field</h5>
                                    <p>Hanoi, the city Filled with the scent of art and culture history.</p>
                                </div>
                                </div>
                                <div class="carousel-item">
                                    <img src="https://cdn.pixabay.com/photo/2020/02/25/04/37/vietnam-4877945_960_720.jpg" class="d-block w-100 h-20" alt="..." height="650">
                                    <div class="carousel-caption d-none d-md-block">
                                    <h5>Saigon</h5>
                                    <p>Hanoi, the city Filled with the scent of art and culture history.</p>
                                </div>
                                </div>
                            </div>
                            <button class="carousel-control-prev" type="button" data-bs-target="#carouselExampleCaptions" data-bs-slide="prev">
                                <span class="carousel-control-prev-icon" aria-hidden="true"></span>
                                <span class="visually-hidden">Previous</span>
                            </button>
                            <button class="carousel-control-next" type="button" data-bs-target="#carouselExampleCaptions" data-bs-slide="next">
                                <span class="carousel-control-next-icon" aria-hidden="true"></span>
                                <span class="visually-hidden">Next</span>
                            </button>
                            </div>

            <div class="col-md-3 mb-5 justify-content-md-start " v-for="item in allVietnam" :key="item.id">
                <div class="card shadow p-0 ">
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