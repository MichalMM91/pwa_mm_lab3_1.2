<!-- poniżej jest template komponentu, którego ścieżka jest podawana w about każdorazowo przy wywołaniu -->
<template>
    <div>
         <img class="img" :src="image"/>
    </div>
   
</template>
<script>
export default {
    name: 'ArrowImage',
    props: {
        image: {
            type: String,
            default: () => 'Pusty string'
        }
    },
    data() {
        return {
            
        }
    },

    created (){
        console.log(this.images)
    }
  }
</script>
<!-- poniżej jest kod css per komponent -->
<style scoped>
.img {
    width: 2vw;
    margin: 0;
}
</style>