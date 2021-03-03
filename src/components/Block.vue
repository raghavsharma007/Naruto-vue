<template>
    <div v-if="showBlock">
        Click Me {{delay}}
    </div>
</template>

<script>
export default {
    props: ['delay'],
    data() {
        return {
            showBlock: false
        }
    },
    mounted() {
        setTimeout(() => {
            this.showBlock = true
        }, this.delay)
    }

}
</script>

<style>

</style>