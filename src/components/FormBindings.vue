<template>
  <div class="try">
    <!-- <h4>{{ msg }}</h4> -->

    <!-- <p>
      We will start learn about Vue.js
    </p> -->

    <!-- <div className="row">
      <div className="form-floating mb-3 col-6">
        <h5>Form Bindings</h5>
        <p> Name </p>
      </div>
      <div className="form-floating mb-3 col-6">
        <input :value="text" @input="onInput" placeholder="Type here">
        <p>{{ text }}</p>
      </div>
    </div>  -->


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
      text: ''
    }
  },
  methods: {
    onInput(e) {
      this.text = e.target.value
    }
  }
}

</script>