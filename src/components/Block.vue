<template>
    <div v-if="showBlock" @click="stopTimer" class="w-1/3 h-1/3 bg-red-500 uppercase rounded-full m-auto text-white text-3xl font-bold flex items-center justify-center border-4 border-red-800">
        Click Me
    </div>
</template>

<script>
export default {
    props: ['delay'],
    data() {
        return {
            showBlock: false,
            timer: null,
            reactionTime: 0
        }
    },
    mounted() {
        setTimeout(() => {
            this.showBlock = true
            this.startTimer()
        }, this.delay)
    },
    methods: {
        startTimer() {
            this.timer = setInterval(() => {
                this.reactionTime += 10
            }, 10)

        },
        stopTimer() {
            clearInterval(this.timer)
            this.$emit('end', this.reactionTime)
        }
    }

}
</script>

<style>

</style>