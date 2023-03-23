<template>
    <main>
        <div class="result">
            <h1 class="result__title">
                Your Result
            </h1>
            <p class="result__score">
                <span class="result__points"> {{ score }} </span>
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
    icon: IconReaction
  },
  {
    category: "Memory",
    score: 92,
    icon: IconMemory
  },
  {
    category: "Verbal",
    score: 61,
    icon: IconVerbal
  },
  {
    category: "Visual",
    score: 72,
    icon: IconVisual
  }
]



const score = ref(76)

</script>

<style lang="scss">
    @import "./assets/styles/main.scss";

    main {
        max-width: 650px;
        margin: 0 auto; 
    }

    .result {
        text-align: center;
    }

    @media screen and (min-width: 768px) {
        main {
            display: grid;
            grid-template-columns: 1fr 1fr;
        }
    }

</style>