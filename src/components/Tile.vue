<template>
    <div class="subject">
        <p class="subject__heading">
            <img :src="subj.icon" alt="" class="subject__icon"> 
            <p class="subject__title"> {{ subj.category }} </p>
        </p>
        <p class="subject__score">
            <span class="subject__points"> {{ subj.score }} </span> / 100
        </p>

    </div>
</template>

<script setup>
    defineProps({
        subj: Object
    })
    
</script>

<style lang="scss" scoped>
    .subject {
        display: flex;
        flex-direction: row;
        justify-content: space-between;
        align-items: center;
        background-color: rgba(255, 0, 0, 0.418);
        padding-inline: 1rem;
        margin-block: 1rem;

        &__heading {
            display: flex;
            gap: 0.5rem;
        }
    }

</style>