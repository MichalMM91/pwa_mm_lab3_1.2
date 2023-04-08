<template>
    
    <div class="modal">
        <div class="column-wrapper" >
            <div class="small-items centered">
                <SmallImages :images="items" @selectedImg="showImg($event)"/>
               
            </div>
        </div>

        <div class="modal-content" @click="closeModal">
            <img :src="image" style="width:600px" >
            
        </div>
    </div>
</template>

<script>
    import SmallImages from '../gallery/smallimages.vue';

    export default{
        components: {SmallImages},
        name: 'Modal',
        props: {
            image: {
            type: String,
            default: () => ''
        },
    },
        methods: {
            closeModal() {
                this.$emit('closeModal', false)
            },
       
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
        background-color: rgba(255, 255, 255, 0.7);
    }
    .column-wrapper{
        width: 30vw;
        height: 80vh;
        margin-top: 30px;
        margin-bottom: auto;
        margin-left: auto;
        margin-right: auto;
        padding: 0;
        align-items: flex-start;
        justify-content: center; 
    }
    .modal-content{

        width: 700px;
        height: 700px;
        margin-top: 30px;
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
        /* display: flex;
        flex-direction: column;
        flex-wrap: wrap;
        text-align: center;
        justify-content: center;
         */
    }

    .centered {
        text-align: center;

    }
</style>