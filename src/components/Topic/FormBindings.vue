<template>
  <div class="try2">
    <p style="margin-top:20px">
      We will start learn about
    </p>
    <h6 :class="titleClass"> Form Bindings </h6>

    <b-container>
        <b-row>
            <b-col md="4"> Please Input Your Name </b-col>
            <b-col md="2">
                <input :value="text" @input="onInput" placeholder="Type here"/>
            </b-col>
        </b-row>
        <b-row>
            <b-col md="6" style="text-align: left; margin-left: 88px; margin-top: 20px;"> Hello, {{ text }}. Have a nice day</b-col>
        </b-row>
    </b-container>


  </div>
</template>

<script>

    export default {
        name: 'FormBindings',
        props: {
            msg: String
        },
        data() {
            return {
                text: '',
                titleClass: 'titleForm'
            }
        },
        methods: {
            onInput(e) {
            this.text = e.target.value
            }
        }
    }

</script>



<style>
    .titleForm {
        color: red;
    }
</style>