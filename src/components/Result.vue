<template>
    <div class="border-dotted border-2 border-blue-700 p-2 font-semibold text-lg w-1/3 m-auto mt-16">
        Reaction Time: {{ score }} ms
    </div>
  
</template>

<script>
export default {
    props: ['score']
}
</script>

<style>

</style>