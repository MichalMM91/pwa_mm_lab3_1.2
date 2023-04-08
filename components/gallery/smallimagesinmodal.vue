 <!-- poniżej jest template komponentu, którego ścieżka jest podawana w about każdorazowo przy wywołaniu -->
 <template>
    <div class="small-images">
        <img class="img" :src="item" v-for="(item,index) in images" :key="index" @click="sendImage(item)">
    </div>
   
</template>
<script>


export default {
    name: 'SmallImagesInModal',
    props: {
        images: {
            type: Array,
            default: () => []
        }
    },
    
    created (){
        console.log(this.images)
    },

    methods: {
        sendImage(url) {
            this.$emit('selectedImg', url)
        }
    }
  };
</script>
<!-- poniżej jest kod css per komponent -->
<style scoped>
.img {
    width: 10vw;
    margin: 10px;
    cursor: pointer;
}
.img:hover {
    border: 1px solid rgb(103, 103, 103);
    width: 11vw;
    margin: 11px;
}

</style>