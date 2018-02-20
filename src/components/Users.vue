<template>
    <div>
        <h3>Users list</h3>
        <ul>
            <li v-for="user in users">{{ user.username }}</li>
        </ul>
    </div>
</template>

<script>
    export default {
        components: {

        },

        data () {
            return {
                users: []
            }
        },

        methods: {
            fetchUsers() {
                fetch("https://jsonplaceholder.typicode.com/users")
                    .then(response => response.json())
                    .then(users => {
                        this.users = users;
                    });
            }
        },

        created() {
            this.fetchUsers();
        }
    }
</script>

<style lang="scss">

</style>