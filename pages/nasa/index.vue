<template>
    <div class="container">
        <h1>Nasa</h1>
        <br>
        <h3>Wyszukiwarka zwraca kolekcję zdjęć z endpointu Nasa<br>
        Należy wprowadzić nazwę planety w języku angielskim </h3>
        <br>
        <div>
        <input v-model="message" placeholder="search..." />
        
        <button @click="$event =>find()">Wyszukaj</button>
        </div>
    <div style="display: flex; flex-wrap: wrap; width: 100%; justify-content: center" >

        <template v-for="value in dataArr">
            <template v-for="(link,index) in value.links">
                <img 
                    @click="setModal(link.href)"
                    alt=""
                    v-if="index===0"
                    :data-index="index"
                    :src="link.href"
                    style="width: 100px; height: 100px; object-fit: cover; padding: 5px"/>   
                    

            
            </template>     
            

        </template>


    </div>
   
    </div>
   </template>
   
   <script >
   
   import axios from "axios";
        export default{
            name: "index",
           
            created() {
                this.fetchData()
            },

            data() {
                return {
                    dataArr: [],
                    message: "earth"
                }
            },

            methods: {
                find() {
                    this.fetchData()
                    
                },
                async fetchData(value) {
                    await axios.get('https://images-api.nasa.gov/search?q='+ this.message)
                        .then(res => {
                            this.dataArr = res.data.collection.items;
                            console.log(res.data.collection.items);
                            this.currentCollection = this.message;
                            

                        })
                        .catch(error =>  {
                            console.log(error)
                        })
                
                },
                setModal(value) {
                    const data = {
                        state: true,
                        content: value,
                    };
                    this.$nuxt.$emit("openModal", data);
                    },
            }

        }


   </script>
   
   <style scoped>
    .nasa{
        display: flex; 
        flex-wrap: wrap; 
        width: 100%; 
        justify-content: center

    }
    .img{
        width: 100px; 
        height: 100px; 
        object-fit: cover; 
        padding: 5px
    }

    .container{
        
        width: 100vw; 
       text-align: center;
       margin: auto;

    }
   </style>
   