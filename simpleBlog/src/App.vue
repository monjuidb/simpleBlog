<script setup>
import axios from 'axios';
import { reactive } from 'vue';

const resData=reactive({

    id:0,
    title: '',
    img: '',
    content: '',
    category_id:0,
    created_at: '',
    updated_at: ''

})

getData();
async function getData() {
 
    const url = 'https://basic-blog.teamrabbil.com/api/post-details/1';
    const response = await axios.get(url);
    resData=response.data['data'];  
}
</script>

<template>
<div>
  <h1>{{ resData.title }}</h1>
  <img :src=resData.img alt=" " class="rounded-sm" />
  <p>{{ resData.content }}</p>

</div>

</template>

<style scoped>


</style>
