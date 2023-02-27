<template>
  <div class="try1">
    <p style="margin-top:20px">
      We will start learn about
    </p>
    <h6 :class="titleClass"> Event Listeners </h6>

    <b-container>
        <b-row class="mt-4">
            <b-col v-for="card in cards" :key="card.id" cols="4">
            <b-card
                :title="`Card ${card.id}`"
                img-top-tag="article"
                class="mb-2"
            >
                <img
                :id="`show-modal-${card.id}`"
                @click="showModal = card.id"
                class="card-img-top"
                :src="require(`../../assets/kota/${card.id}.jpg`)"
                alt="Image"
                />
                <b-card-text> Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut. </b-card-text>
                <b-card-text> Total Like : {{ card.count }} </b-card-text>
            </b-card>
            <button @click="increment(card.id)"> Like </button>
            <button @click="decrement(card.id)" style="margin-left:20px"> Dislike </button>
            <!-- <Teleport to="body">
                <modal
                :show="showModal === card.id"
                @close="showModal = null"
                >
                <template #header>
                    <h3>custom header</h3>
                </template>
                </modal>
            </Teleport> -->
            </b-col>
        </b-row>
    </b-container>


  </div>
</template>

<script>

    // import Modal from '../Topic/ModalEvent.vue'

    export default {
        name: 'EventListeners',
        data() {
            return {
                titleClass: 'titleEvent',
                count: 0,
                showModal: false,
                cards: [
                    { id: 1, count: 0 },
                    { id: 2, count: 0 },
                    { id: 3, count: 0 }
                ]
            }
        },
        // components: {
        //     Modal
        // },
    methods: {
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
    }

    }

</script>


<style>
    .titleEvent {
        color: blue;
    }
</style>