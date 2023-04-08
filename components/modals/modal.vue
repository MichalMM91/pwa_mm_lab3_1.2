<template>
    
    <div class="modal">
        <div class="column-wrapper" >
            <div class="small-items centered">
                <SmallImagesInModal :images="items" @selectedImg="showImage($event)"/>
            </div>
        </div>
        
        <div class="modal-content">
            <img :src="image" style="width:65vw" >
            
        </div>

        <div>
            <button class="button-close" @click="closeModal">X</button>
        </div>
    </div>
</template>

<script>
    import SmallImagesInModal from '../gallery/smallimagesinmodal.vue';
    export default{
        name: 'Modal',
        
        components: {SmallImagesInModal},
        
        props: {
            image: {
            type: String,
            default: () => ''
            },
            
        },
        
        created (){
             console.log('on create') 
        },

        methods: {
            closeModal() {
                this.$emit('closeModal', false)
            },
            showImage(url) {
                this.image = url;
            }
        },
        data() {
            return {
                items: [
                    'https://img.freepik.com/premium-zdjecie/zloto-czarny-zegarek-z-niebieska-tarcza-i-czerwonymi-wskazowkami_534373-3181.jpg?w=1060',
                    'https://img.freepik.com/premium-zdjecie/nowoczesny-zegarek-na-reke-z-bliska_488220-21996.jpg?w=1060',
                    'https://img.freepik.com/premium-zdjecie/mechaniczny-zegarek-na-reke-na-czarnym-tle-zblizenie_508835-446.jpg?w=1060'
                ],
            };
        },
    
};
</script>

<style scoped>
    .modal{
        display: flex;
        position: absolute;
        left: 0;
        top: 0;
        width: 100vw;
        height: 100vh;
        background-color: rgba(255, 255, 255, 0.4);
    }
    .column-wrapper{
        width: 20vw;
        height: 80vh;
        margin-top: 50px;
        margin-bottom: auto;
        margin-left: auto;
        margin-right: auto;
        padding: 0;
        align-items: flex-start;
        justify-content: center; 
    }
    .modal-content{

        width: 80vw;
        margin-top: 50px;
        margin-bottom: auto;
        margin-left: auto;
        margin-right: auto;
        padding: 0;
        width: 70%;
        align-items: center;
        justify-content: center; 
    }

    .small-items {
        width: 100px;
        
    }

    .centered {
        text-align: center;

    }

    .button-close {
        width: 4vw;
        height: 4vw;
        min-height: 30px;
        min-width: 30px;        
        margin-top: 50px;
        margin-right: 50px;
        border-radius: 25%;
        transition-duration: 0.4s;
        font-size: large;
        background-color: rgb(7, 60, 130);
        color: azure;
    }
    .button-close:hover {
        cursor:pointer;
        background-color: #c90f0fa7;
        color: black;
    }

</style>