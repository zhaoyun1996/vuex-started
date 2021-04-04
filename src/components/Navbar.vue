<template>
    <div class="navbar">
        <h1>My Vuex App Todos</h1>
        <ul>
            <li>Home</li>
            <li>About</li>
            <li v-if="auth.isAuthenticated">
                Total Todos: {{ todos.length }}
                <button>Logout</button>
            </li>
            <li v-else>Login</li>
        </ul>
    </div>
</template>

<script>
import {mapState} from 'vuex'
export default {
    name: 'Navbar',
    computed: mapState(['todos', 'auth'])
}
</script>

<style scoped>
.navbar {
    padding: 5px;
    text-align: center;
    background: rgb(240, 240, 240);
    color: #000;
}

.navbar ul {
    display: flex;
    justify-content: space-around;
    align-items: center;
    list-style: none;
    padding: 0;
}
</style>