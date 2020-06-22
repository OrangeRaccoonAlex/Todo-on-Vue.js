<template>
    <h1>{{ appName }}</h1>
</template>

<script>
export default {
    name: 'Header',
    props: {
        appName: {
            type: String,
            required: true,
        }
    },
}
</script>

<style>

</style>