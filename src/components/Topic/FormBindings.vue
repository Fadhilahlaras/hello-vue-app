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
                titleClass: 'titleForm',
                regex: /^[a-zA-Z]*$/, // regular expression untuk huruf saja
                duration: 1000 
            }
        },
        methods: {
            onInput(event) {
                // this.text = e.target.value
                const inputText = event.target.value;
                if (this.regex.test(inputText)) {
                    this.text = inputText;
                } else {
                    alert("This field can only be filled with text input. Please check it again.");
                    event.target.value = this.text;
                        setTimeout(() => {
                            // alert(null);
                        }, this.duration);
                }
            }
        }
    }

</script>



<style>
    .titleForm {
        color: red;
    }
</style>