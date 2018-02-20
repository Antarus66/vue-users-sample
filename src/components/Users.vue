<template>
    <div>
        <h3>Users list</h3>
        <div class="user-list">
            <user-item
                    v-for="user in users"
                    :key="user.id"
                    :user="user"
                    @deletedUser="deleteUser"
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
            },
            deleteUser(user) {
                let i = this.users.indexOf(user);

                if (i !== -1) {
                    this.users.splice(i, 1);
                }
            }
        },

        created() {
            this.fetchUsers();
        }
    }
</script>

<style scoped lang="scss">
    .user-list {
        width: 300px;
        margin: auto;
    }
</style>