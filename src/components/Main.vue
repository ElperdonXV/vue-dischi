<template>
    <main>
        <div class="container">
            <div class="row albums">
                <div :key="index" v-for="(album, index) in albums" class="col-3 p-3 album">
                    <img :src="album.poster" alt="">
                    <h2>{{album.title}}</h2>
                    <h3>{{album.author}}</h3>
                    <h4>{{album.year}}</h4>
                </div>
            </div>
        </div>
    </main>
</template>

<script>
import axios from 'axios';
export default {
    name: 'Main',
    data (){
        return{
            albums : null,
        }
    },
    mounted(){
        axios.get('https://flynn.boolean.careers/exercises/api/array/music')
        .then((result) =>{
            this.albums = result.data.response;
            console.log(this.albums);

        })
        .catch((error) =>{
            console.log(error);
        })
    }
}
</script>

<style>

</style>