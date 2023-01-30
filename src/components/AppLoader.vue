<script>
export default {
    name: 'AppLoader'
}
</script>

<template>
    <div class="overlay text-center pt-5 text-light">
        <div class="fs-5 text-uppercase">loading...</div>
    </div>

</template>

<style scoped lang="scss">
@use '../assets/scss/partials/variables.scss' as *;

.overlay {
    position: fixed;
    top: 0;
    bottom: 0;
    left: 0;
    right: 0;
    background-color: $bg-black;
}
</style>