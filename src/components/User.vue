<template>
    <div class="item">
        <button v-on:click="deleteUser(user)">x</button>
        <span> {{ user.username }}</span>
    </div>
</template>

<script>
    export default {
        props: {
            user: {
                type: Object,
                required: true
            }
        },
        data() {
            return {};
        },
        methods: {
            deleteUser(user) {
                this.$emit("deleteUser", user);
            }
        }
    }
</script>

<style scoped lang="scss">
    .item {
        text-align: left;
        padding: 5px;
    }
</style>