<template>
    <div class="container">
        <div class="row">
            <input type="text" size="20" class="input-sm" v-model="title" @keyup.enter="find(title)">
            <button type="button" class="btn-sm btn-danger" @click="find(title)" >검색</button>
        </div>
        <div class="row">
            <div class="col-md-4" v-for="(youtube,index) in youtubes" :key="index">
                <div class="thumbnail">
                    <iframe style="width:280px;height: 180px;"
                        :src="`https://www.youtube.com/embed/${youtube.id.videoId}`">
                    </iframe>
                    <div class="caption">
                        <p v-html="youtube.snippet.channelTitle"></p>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script setup>
import {ref, onMounted} from 'vue'

const title = ref("부산여행")
const youtubes=ref([])
console.log(title)
onMounted(()=>{
    find("부산여행")
})

const find= async(title)=>{
    try {
        const response = await fetch(
            `https://youtube.googleapis.com/youtube/v3/search?part=snippet&maxResults=12&q=${title}&type=video&key=AIzaSyAMWLeRTNQP4-w6xPJIUDUv4ORIbGsjSgU`
        )
        const result = await response.json()
        console.log(result.items)
        youtubes.value = result.items
    } catch (error) {
        console.log(
            "error", error
        )
    }
}

</script>

<style scoped>
.row {
    margin: 0px auto;
    width: 960px;
}

p {
    overflow: hidden;
    white-space: nowrap;
    text-overflow: ellipsis;
}
</style>