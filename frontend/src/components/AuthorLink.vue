<template>
  <router-link
    :to="`/author/${author.user.username}`"
    >
    {{displayName}}
    </router-link>
</template>

<script>
export default {
    name: 'AuthorLink',
    props: {
        author: {
            type: Object,
            required: true,
        },
    },
    computed: {
        displayName () {
            return (
                this.author.user.firstname &&
                this.author.user.lastname &&
                `${this.author.user.firstname} ${this.author.user.lastname}`
            ) || `${this.author.user.username}`
        },
    },

}
</script>

<style>

</style>