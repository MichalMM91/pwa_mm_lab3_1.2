<template>
    <div>
        <!-- <TopNav /> -->
        
        <h1 class="centered">Galeria zegarków</h1>
        <!-- w divie wrappera znajdują się tagi odnoszące się do komponentów ze wskazaniem adresu w parametrze image -->
        <div class="wrapper">
            <div class="img-big centered">
                <BigImage :image="img" @rm="runModal($event)"/>
            </div>
            <div class="line-wrapper">

                <div class="small-items centered">
                    <SmallImages :images="items" @selectedImg="showImg($event)"/>
                </div> 

                <Modal v-show="showModal" :image="img" @closeModal="runModal($event)"/>
            </div>
            
        </div>
        
    </div>
        
</template>

<script>
/* poniżej importuję komponenty z folderu components */
import BigImage from '~/components/gallery/bigimage.vue';
import SmallImages from '~/components/gallery/smallimages.vue';
import TopNav from '../components/nav/TopNav.vue';
import Modal from '~/components/modals/modal.vue';

export default {
    name: 'Gallery',
    components: { TopNav, BigImage, SmallImages, Modal },
    data() {
       return {
        items: [
        'https://img.freepik.com/premium-zdjecie/zloto-czarny-zegarek-z-niebieska-tarcza-i-czerwonymi-wskazowkami_534373-3181.jpg?w=1060',
        'https://img.freepik.com/premium-zdjecie/nowoczesny-zegarek-na-reke-z-bliska_488220-21996.jpg?w=1060',
        'https://img.freepik.com/premium-zdjecie/mechaniczny-zegarek-na-reke-na-czarnym-tle-zblizenie_508835-446.jpg?w=1060'
        ],

        img : 'https://img.freepik.com/premium-zdjecie/zloto-czarny-zegarek-z-niebieska-tarcza-i-czerwonymi-wskazowkami_534373-3181.jpg?w=1060',

        showModal: false 
       } 
    },
    methods: {
        showImg(url) {
            console.log('to jest ten event')
            this.img=url
            console.log(url)
        },

        runModal(e) {
            console.log(e)
            this.showModal = e
        },

        }
    };

</script>
<style scoped>
/* poniżej zawieram kod css strony about */
.colorRed {
    color: red;
}

.img-big {
    width: 40vw;
    display: flex;
    flex-direction: row;
    text-align: center;
    justify-content: center;
    margin: auto;
}

.small-items {
    width: 60vw;
    height: 18vh;
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    text-align: center;
    justify-content: center;
    margin-left: 15px;
    margin-right: 15px;
    margin-top: auto;
    margin-bottom: auto;
    background-color: rgba(222, 219, 219, 0.648);
}

.centered {
    text-align: center;

}

.wrapper {
    width: 100vw;
    text-align: center;
    justify-content: center;
}

.line-wrapper {
    width: 80vw;
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    text-align: center;
    justify-content: center;
    margin: auto;
}

.arrow{
    padding: auto;
}

</style>