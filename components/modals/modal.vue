<template>
    
    <div class="modal">
        
        <div class="modal-content" >
            <img :src="image" style="width:600px" >
            
        </div>

        <div class="modal-content" >
            <img :src="image" style="width:600px" @click="closeModal()">
            
        </div>
    </div>
</template>

<script>
    export default{
        name: 'Modal',
        props: {
            image: {
            type: String,
            default: () => ''
        },
        methods: {
            closeModal() {
                this.$emit('closeModal', false)
            }
        },
        
    }
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

    .modal-content{
       /*  background-color: white;
        width: 600px;
        height: 600px;
        position: absolute; */
/*         left: calc(50vw-300px);
        top: calc(50vh-300px);
        align-items: center;
        justify-content: center; */

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
</style>