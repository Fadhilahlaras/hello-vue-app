<template>
  <div id="footerview">
    <!-- <p> Developed by {{msg}} </p> -->
    <b-navbar style="margin-top:100px" toggleable="lg" type="dark" variant="info">
        <p>&copy; <a href="https://github.com/Fadhilahlaras">{{msg}}</a>, All Right Reserved.</p>
    </b-navbar>
  </div>
</template>


<script>

    export default {
        name: 'FooterView',
        props: {
            msg: String
        },
    }

</script>