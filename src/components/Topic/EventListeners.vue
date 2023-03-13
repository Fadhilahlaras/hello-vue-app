<template>
  <div class="try1">
    <p style="margin-top:20px">
      We will start learn about
    </p>
    <h6 :class="titleClass"> Event Listeners </h6>

    <b-container>
        <b-row class="mt-4">
            <b-col v-for="card in cards" :key="card.id" cols="4" class="p-3">
            <b-card
                :title="`Card ${card.id}`"
                img-top-tag="article"
                class="mb-2"
                @click="showModal(card.id, card.title, card.message)"

            >
                <img
                :id="`show-modal-${card.id}`"
                class="card-img-top"
                :src="require(`../../assets/kota/${card.id}.jpg`)"
                alt="Image"
                width="300px" 
                height="300px"
                />
                <b-card-text> {{ card.text }} </b-card-text>
                <b-card-text> Total Like : {{ card.count }} </b-card-text>
            </b-card>
            <button @click="increment(card.id)"> Like </button>
            <button @click="decrement(card.id)" style="margin-left:20px"> Dislike </button>
            <b-modal v-model="show" :title="`${selectedCardTitle} City`">
                <!-- <b-img :src="require(`../../assets/kota/${selectedCard}.jpg`)" fluid alt="Image" /> -->
                <b-card-text>{{ selectedCardMessage }}</b-card-text>            
            </b-modal>
            </b-col>
        </b-row>
    </b-container>
  </div>
</template>

<script>

    // import Modal from '../Topic/ModalEvent.vue'
    import { BCard, BCardText, BModal } from 'bootstrap-vue'

    export default {
        name: 'EventListeners',
        components: {
            BCard,
            BCardText,
            BModal,
            // BImg,
        },
        data() {
            return {
                titleClass: 'titleEvent',
                count: 0,
                cards: [
                    { id: 1, count: 0, title: "DKI Jakarta", message: "Jakarta is the capital and most populous city of the Republic of Indonesia. Located on the northwest coast of the worlds most populous island of Java, Jakarta is the countrys economic, cultural and political center. The official metropolitan area, known as Jabodetabek (a name formed by combining the initial syllables of Jakarta, Bogor, Depok, Tangerang and Bekasi), is the second largest in the world." },
                    { id: 2, count: 0, title: "Surabaya", message: "Surabaya is the second largest city in Indonesia after Jakarta. Surabaya is also a Centre for business, Commerce, industry, and education in East Java as well as the eastern Indonesia region." },
                    { id: 3, count: 0, title: "Bandung", message: "Bandung is the capital of West Java in Indonesia. Bandung is 180 kilometers southeast from Jakarta. Although it has a population of over two million the pace of city life is slower than Jakarta." },
                    { id: 4, count: 0, title: "Jogyakarta", message: "A vacation in Indonesia gives tons of unforgettable experience to tourists. The country even has some special regions, including Yogyakarta City. People also call it Jogja. The location is in Java Island and it is known for numerous allures like culture, traditional foods, natural attractions, beaches, arts, and much more" },
                    { id: 5, count: 0, title: "Bali", message: "Bali, the famed Island of the Gods, with its varied landscape of hills and mountains, rugged coastlines and sandy beaches, lush rice terraces, and volcanic hillsides all providing a picturesque backdrop to its colorful, deeply spiritual, and unique culture stakes a serious claim to be paradise on earth"}
                ],
                selectedCard: 1,
                selectedCardTitle: 1,
                selectedCardMessage: 0,
                show: false
            }
        },
        // components: {
        //     Modal
        // },
        methods: {
            showModal(id, title, message) {
                console.log(id)
                this.selectedCard = id
                this.selectedCardMessage = message;
                this.selectedCardTitle = title;
                this.show = true
                console.log(message)

            },
            increment(cardId) {
                const card = this.cards.find(c => c.id === cardId)
                card.count++
            },
            decrement(cardId) {
                const card = this.cards.find(c => c.id === cardId)
                if(card.count <= 0) {
                    alert("The count already 0")
                } else {
                    card.count--
                }
            }
        },       
    }
</script>


<style>
    .titleEvent {
        color: blue;
    }
</style>