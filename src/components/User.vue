<template>
    <div>{{ user.username }}</div>
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
        }
    }
</script>

<style lang="scss">

</style>