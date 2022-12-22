<template>
  <div class="try1">
    <p style="margin-top:20px">
      We will start learn about
    </p>
    <h6 :class="titleClass"> Event Listeners </h6>

    <b-container>
        <b-row class="mt-4">
            <b-col cols="4">
                <b-card
                    title="Card 1"
                    img-top-tag="article"
                    class="mb-2"
                    >
                    <img class="card-img-top" src="" alt="Image">
                    <b-card-text> Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut. </b-card-text>
                    <b-card-text> Total Like : {{ count }} </b-card-text>
                </b-card>
                <button @click="increment"> Like </button>
                <button @click="decrement" style="margin-left:20px"> Dislike </button>


            </b-col>
            <b-col cols="4">
                <b-card
                    title="Card 2"
                    img-src="./assets/logo.png"
                    img-alt="Image"
                    img-top-tag="article"
                    class="mb-2"
                    >

                    <b-card-text> Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut. </b-card-text>
                </b-card>
            </b-col>
            <b-col cols="4">
                <b-card
                    title="Card 3"
                    img-src="./assets/logo.png"
                    img-alt="Image"
                    img-top-tag="article"
                    class="mb-2"
                    >

                    <b-card-text> Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut. </b-card-text>
                </b-card>
            </b-col>
        </b-row>
    </b-container>


  </div>
</template>

<script>

    export default {
        name: 'EventListeners',
        data() {
            return {
                titleClass: 'titleEvent',
                count: 0
            }
        },
    methods: {
        increment() {
            this.count++
        },
        decrement() {
            if(this.count <= 0) {
                alert("The count already 0, cannot decrement again")
            } else {
                this.count--
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