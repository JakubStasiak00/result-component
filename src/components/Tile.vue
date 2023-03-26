<template>
    <div class="subject" :class="color">
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
import { ref } from 'vue';

    const props = defineProps({
        subj: Object
    })

    const color = ref(`subject--${props.subj.color}`)

    
</script>

<style lang="scss">
    @use "sass:color";
    @import "../assets/styles/main.scss";

    .subject {
        display: flex;
        flex-direction: row;
        justify-content: space-between;
        align-items: center;    
        margin-block: 1rem;
        padding: 1rem; 
        border-radius: 0.5rem;

        &__heading {
            display: flex;
            gap: 0.5rem;
        }

        &--red {
            background-color: color.adjust($component-red, $alpha: -0.9);

            .subject__title {
                color: $component-red;
            }
        }

        &--yellow {
            background-color: color.adjust($component-yellow, $alpha: -0.9);

            .subject__title {
                color: $component-yellow;
            }
        }

        &--green {
            background-color: color.adjust($component-green, $alpha: -0.9);

            .subject__title {
                color: $component-green;
            }
        }

        &--blue {
            background-color: color.adjust($component-blue, $alpha: -0.9);

            .subject__title {
                color: $component-blue;
            }
        }

        &__score {
            color: color.adjust($neutral-dark-blue, $alpha: -0.5);
            font-weight: $font-weight-bold;
        }

        &__points {
            color: $neutral-dark-blue;
        }
    }

</style>