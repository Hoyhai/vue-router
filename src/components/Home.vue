<template>
    <div class="box">
        <h1>Random Dog</h1>
        <Button @click="handleSearch()" type="primary">Search</Button>
        <div class="cardBox">
            <h2 v-if="!data">Wait for a click</h2>
            <Card dis-hover :bordered="false" v-if="data">
                <div class="image">
                    <img :src=data[0].url>
                </div>
            </Card>
        </div>
    </div>
</template>

<script>    
export default {
    data() {
        return {
            data: ''
      }
    },
    name: 'Home',
    methods: {
        handleSearch() {
            const url = 'https://api.thedogapi.com/v1/images/search?size=med&mime_types=jpg&format=json&has_breeds=true&order=RANDOM&page=0&limit=1'
            fetch(url)
                .then(res => res.json())
                .then(json => {
                    console.log(json)
                    this.data = json 
                })
        }
    }
}
</script>

<style>
.box {
    display: block;
    margin: 0 auto;
    width: 30%;
    justify-content: center;
    text-align: center;
}

ul {
    display: flex;
}

img {
    border-radius: 8px;
    width: 320px;
    height: 300px;
}
@media only screen and (max-width: 768px) {
    img {
    border-radius: 8px;
    width: 220px;
    height: 200px;
}
}
.cardBox {
    width: 100%;
    height: 100%;
    display: flex;
    margin: 0 auto;
    justify-content: center;
}
</style>
