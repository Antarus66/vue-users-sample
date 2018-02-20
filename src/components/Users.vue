<template>
    <div>
        <h3>Users list</h3>
        <div>
            <user-item
                    v-for="user in users"
                    :key="user.id"
                    :user="user"
            />
        </div>
    </div>
</template>

<script>
    import User from "./User.vue";

    export default {
        components: {
            "user-item": User
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