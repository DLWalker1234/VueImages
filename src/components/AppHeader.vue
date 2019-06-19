<template>
    <div class="NavBar">
        <router-link to="/" id="logo">Image Storage</router-link>
        
        <div id="RightMenu">
            <div v-if="isLoggedIn">
                <router-link to="/" class="item">Galleries</router-link>
                <router-link to="/pload" class="item">Upload</router-link>
                <a class="item" @click="logout">LogOut</a>
            </div>
            <a v-else href="#" class="item" @click="login">Login</a>
        </div>
    </div>
</template>

<script>
import { mapActions, mapGetters } from 'vuex';

export default {
    name: 'AppHeader',
    computed: mapGetters(['isLoggedIn']),
    methods: {
        ...mapActions(['login', 'logout'])
    }
}
</script>

<style>

.NavBar {
    display: flex;
}

#logo {
    flex-grow: 1;
}

.item {
    padding: 5%;
    text-align: center;
    color: black;
}

.item:hover {
    background-color: #ccc;
    color: white;
}
</style>


