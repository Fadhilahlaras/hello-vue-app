<template>
  <div id="headerView">
    <b-navbar toggleable="lg" type="dark" variant="info">
        <b-navbar-brand href="#/home">Home</b-navbar-brand>
        <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>
        <!-- Show other navbar -->
        <b-collapse id="nav-collapse" is-nav>
            <b-navbar-nav>
                <b-nav-item href="#">About</b-nav-item>
                <b-nav-item href="#">Contacts</b-nav-item>
                <b-nav-item-dropdown>
                    <template v-slot:button-content>
                        Topic
                    </template>
                    <b-dropdown-item href="#/form-bindings">Form Bindings</b-dropdown-item>
                </b-nav-item-dropdown>
            </b-navbar-nav>

            <!-- Right aligned nav items -->
            <b-navbar-nav class="ml-auto">
                <b-nav-item-dropdown text="Lang" right>
                <b-dropdown-item href="#">EN</b-dropdown-item>
                <b-dropdown-item href="#">ES</b-dropdown-item>
                <b-dropdown-item href="#">RU</b-dropdown-item>
                <b-dropdown-item href="#">FA</b-dropdown-item>
                </b-nav-item-dropdown>
                <b-nav-item-dropdown right>
                    <!-- Using 'button-content' slot -->
                    <template v-slot:button-content>
                        <em>User</em>
                    </template>
                    <b-dropdown-item href="#">Profile</b-dropdown-item>
                    <b-dropdown-item href="#">Sign Out</b-dropdown-item>
                </b-nav-item-dropdown>
            </b-navbar-nav>
        </b-collapse>
    </b-navbar>
  </div>
</template>

<script>

import Vue from 'vue';

import BootstrapVue from 'bootstrap-vue'
import 'bootstrap/dist/css/bootstrap.css'
import 'bootstrap-vue/dist/bootstrap-vue.css'
Vue.use(BootstrapVue)


export default {
  name: 'headerView',
}
</script>
<style>
</style>