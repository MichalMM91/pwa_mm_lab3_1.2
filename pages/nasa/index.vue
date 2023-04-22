<template>
    <div>
    <h1>Nasa</h1>
   <div>
    <input v-model="message" placeholder="search..." />
    <button @click="$event =>find()">SEARCH</button>
   </div>
   <div style="display: flex; 
            flex-wrap: wrap; width: 100vw; 
            justify-content: center">
        <img
        :src="value.links[0].href"
        v-for="(value, index) in dataArr"
        :key="index"
        style="width: 100px; height: 100px; 
        object-fit: cover; padding: 5px"/>
        
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
                    message: "sun"
                }
            },

            methods: {
                find() {
                    this.fetchData()
                    
                },
                async fetchData() {
                    await axios.get('https://images-api.nasa.gov/search?q='+this.message)
                        .then(res => {
                            this.dataArr = res.data.collection.items;
                        })
                        .catch(error =>  {
                            console.log(error)
                        })
                
                }
            }

        }


   </script>
   
   <style scoped>
   </style>
   