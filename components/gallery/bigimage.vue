<!-- poniżej jest template komponentu, którego ścieżka jest podawana w about każdorazowo przy wywołaniu -->
<template>
    <div>
         <img class="img" :src="image" @click="showModal"/>
    </div>
   
</template>
<script>
export default {
    name: 'BigImage',
    props: {
        image: {
            type: String,
            default: () => ''
        }
    },

    methods: {
        showModal() {
            this.$emit('rm', true)
        }
    },

    
  };
</script>
<!-- poniżej jest kod css per komponent -->
<style scoped>
.img {
    width: 100%;
    margin: 10px;
    cursor: pointer;
}
</style>