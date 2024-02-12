<template>
    <div class="container mt-4">
        <div class="row">

            <div class="col-md-5 mb-1 mx-auto">
                <div class="card shadow">
                    <div class="card-header p-0">
                        <img src="https://cms.dmpcdn.com/travel/2022/03/31/e60f6880-b0c8-11ec-a7ab-a509bef14ff5_webp_original.jpg" class="card-img-top" alt="wonders">
                    </div>
                </div>
            </div>

            <div class="col-md-6 mx-auto">
                <div class="card shadow">
                    <div class="card-header bg-danger">
                        <span class="text-white fs-5">
                            ลงทะเบียนที่เที่ยวเวียดนาม
                        </span>
                    </div>
                    <div class="card-body text-success">
                        <form @submit.prevent="addWonder">
                            <div class="mb-1">
                                <label for="">ชื่อที่เที่ยวเวียดนาม</label>
                                <input type="text" class="form-control" v-model="wonderState.name" />
                            </div>
                            <div class="mb-1">
                                <label for="">ตำแหน่ง ที่อยู่ ที่เที่ยวเวียดนาม</label>
                                <input type="text" class="form-control" v-model="wonderState.label" />
                            </div>
                            <div class="mb-1">
                                <label for="">ลิงค์ภาพที่เที่ยวเวียดนาม</label>
                                <input type="text" class="form-control" v-model="wonderState.imageUrl" />
                            </div>

                            <div class="mb-1">

                                <button type="submit" class="btn btn-danger text-white shadow">
                                    ลงทะเบียนที่เที่ยวเวียดนาม
                                </button>
                            </div>
                        </form>
                    </div>
                </div>
            </div>

        </div>
    </div>
</template>

<script setup>
import axios from 'axios'
import { reactive } from 'vue';
import { useRouter } from 'vue-router';

const wonderState = reactive({
    name: '',
    location: '',
    imageUrl:''
})

const router = useRouter()

const addWonder = async () => {
    await axios.post(`https://server-json-774h.onrender.com/Vietnam`,wonderState)
        .then(() => {
            console.log(wonderState)
            router.push({name:'wonders'})
        })
    alert('ลงทะเบียนสิ่งมหัศจรรย์ของโลก เรียบร้อยแล้ว')
}
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Sarabun&display=swap');

.container {
    font-family: 'Sarabun', sans-serif;

}

.form-label {
    color: green;
}
</style>