<template>
    <main>
        <div class="result">
            <h1 class="result__title">
                Your Result
            </h1>
            <p class="result__score">
                <span class="result__points"> {{ score }} </span><br>
                of 100
            </p>
            <p class="result__message">
                <p class="result__grade">
                    Great
                </p>
                <p class="result__description">
                    You scored higher than 65% of the people who have taken these tests.
                </p>
            </p>
        </div>

        <div class="summary">
            <h2 class="summary__title">
                Summary
            </h2>
            <div class="summary__skills">
                <Tile v-for="(subject, index) in dataArray" :key="dataArray[index].category" :subj="subject"  />
            </div>
            <button class="summary__continue"> Continue </button>
        </div>
    </main>
</template>

<script setup>
import { ref } from "vue";
import Tile from "./components/Tile.vue"
import IconMemory from "./assets/images/icon-memory.svg"
import IconReaction from "./assets/images/icon-reaction.svg"
import IconVerbal from "./assets/images/icon-verbal.svg"
import IconVisual from "./assets/images/icon-visual.svg"

const dataArray = [
{
    category: "Reaction",
    score: 80,
    icon: IconReaction,
    color: 'red' //['0', '100%', '67%']
  },
  {
    category: "Memory",
    score: 92,
    icon: IconMemory,
    color: 'yellow'  //['39', '100%', '56%']
  },
  {
    category: "Verbal",
    score: 61,
    icon: IconVerbal,
    color: 'green'  //['166', '100%', '37%']
  },
  {
    category: "Visual",
    score: 72,
    icon: IconVisual,
    color: 'blue'  //['234', '85%', '45%']
  }
]



const score = ref(76)

</script>

<style lang="scss">
    @import "./assets/styles/main.scss";

    main {
        max-width: 638px;
        margin: 0 auto; 
        box-shadow: .5rem 1rem 2rem rgba(43, 51, 163, 0.185);
        min-height: 100vh;

        & > * {
            padding: 1rem;
        }
    }

    .result {
        text-align: center;
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        background: $background-gradient;
        color: hsla(0, 0%, 100%, 0.85);
        align-items: center;
        gap: 2rem;
        border-radius: 0 0 2rem 2rem;
        padding-block: 2rem 3rem;

        &__score {
            background: $circle-gradient;
            aspect-ratio: 1/1;
            width: max-content;
            border-radius: 1000vw;
            padding: 1.5rem;
        }

        &__points {
            font-size: $font-size-900;
            font-weight: $font-weight-bold;
        }

        &__points, &__grade {
            color: white;
        }

        &__message {
            display: flex;
            flex-direction: column;
            gap: 1rem;
        }

        &__grade {
            font-size: $font-size-400;
        }

        &__description {
            font-size: $font-size-100;
            max-width: 70%;
            margin: 0 auto;
        }
    }

    .summary {
        display: flex;
        flex-direction: column;
        gap: 0.5rem;
        padding-block: 2rem 2rem;

        &__title {
            font-weight: $font-weight-black;
            letter-spacing: 0.03rem;
            color: $neutral-dark-blue;
            font-size: $font-size-300;
        }

        &__continue {
            border: none;
            background-color: $neutral-dark-blue;
            color: $neutral-pale-blue;
            border-radius: 100vw;
            padding-block: 1rem;

            &:active, &:hover {
                background: $background-gradient;
                cursor: pointer;
            }
        }
    }

    @media screen and (min-width: 628px) {
        #app {
            display: grid;
            place-items: center;
            min-width: 100vw;
            min-height: 100vh;
        }

        main {
            display: grid;
            grid-template-columns: 1fr 1fr;
            border-radius: 2rem;
            min-height: 0;
        }

        .result {
            border-radius: 2rem;
        }
    }

</style>