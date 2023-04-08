<template>
    <div>
        <TopNav />
        
        <h1 class="centered">Galeria zegarków</h1>
        <!-- w divie wrappera znajdują się tagi odnoszące się do komponentów ze wskazaniem adresu w parametrze image -->
        <div class="wrapper">
            <div class="img-big centered">
                <BigImage :image="img" @rm="runModal($event)"/>
            </div>
            <div class="line-wrapper">

                <div class="arrow">
                    <ArrowImage image="https://cdn-icons-png.flaticon.com/512/275/275203.png?w=740&t=st=1680877096~exp=1680877696~hmac=c0a4b40befae097712eefc32063676fa1b8e86b5a4624882c3bd873a7ea4723f"/>
                </div>

                <div class="small-items centered">
                    <SmallImages :images="items" @selectedImg="showImg($event)"/>
                </div> 

                <div class="arrow">
                    <ArrowImage image="https://cdn-icons-png.flaticon.com/512/156/156324.png?w=740&t=st=1680877098~exp=1680877698~hmac=7a0f82216d2e948d89d6cad1a34a9d0ac1d430aee121d9f2aafd7ea47b8c7dd8"/>
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
import ArrowImage from '~/components/gallery/arrowimage.vue';
import TopNav from '../components/nav/TopNav.vue';
import Modal from '~/components/modals/modal.vue';

export default {
    name: 'Gallery',
    components: { TopNav, BigImage, SmallImages, ArrowImage, Modal },
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
    height: 20vh;
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