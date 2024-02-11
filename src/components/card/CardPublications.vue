<script>
import goUp from './goUp.vue';
import quantumList from './dataJs/publications/quantum';
import machineList from './dataJs/publications/machineLearning';

export default {
    data() {
        return {
            quantumList: quantumList,
            machineLearningList: machineList
        }
    },
    components: { goUp },
}
</script>

<template>
    <div id="my_card">
        <p class="title">Publications</p>
        <div class="body">
            <!-- LISTA Quantum Artificial Intelligence -->
            <h3 class="bold name_section">Quantum Artificial Intelligence</h3>
            <ul>
                <li v-for="item in quantumList">
                    <a v-if="item.link" class="high_contrast" :href="item.link"><i class="fa-solid fa-arrow-right"></i></a>
                    <i v-else class="fa-solid fa-arrow-right"></i>
                    <p>
                        <span>{{ item.normal }} In: </span>
                        <span class="italic">{{ item.italic }}</span>
                    <p>{{ item.when }}</p>
                    <p v-if="item.info">{{ item.info }}</p>
                    </p>
                </li>
            </ul>

            <!-- LISTA Machine Learning -->
            <h3 class="bold name_section">Machine Learning</h3>
            <ul>
                <li v-for="item in machineLearningList">
                    <a v-if="item.link" class="high_contrast" :href="item.link"><i class="fa-solid fa-arrow-right"></i></a>
                    <i v-else class="fa-solid fa-arrow-right"></i>
                    <p>
                        <span>{{ item.normal }} In: </span>
                        <span class="italic">{{ item.italic }}</span>
                    <p>{{ item.when }}</p>
                    <p v-if="item.info">{{ item.info }}</p>
                    </p>
                </li>
            </ul>
        </div>

        <div class="up">
            <goUp />
        </div>
    </div>
</template>

<style scoped lang="scss">
@use "../../style/variables" as *;

#my_card {
    width: 70%;
    margin: 0 auto;
    height: 100%;
    text-align: left;
    font-size: medium;

    .title {
        font-size: 3.5rem;
        margin-bottom: 2rem;
    }

    * {
        margin-bottom: .3rem;
    }

    ul {
        list-style-type: none;

        li {
            margin-bottom: 1.5rem;
            display: flex;
            gap: .5rem;

            * {
                margin-bottom: .3rem;
            }

            a {
                color: $colorHighContrast;

                &:hover {
                    color: $colorFont;
                }
            }
        }
    }

    .name_section {
        margin: 2rem 0 1rem;
        text-decoration: underline;
    }

    .italic {
        font-style: italic;
    }
}

@media screen and (max-width: 900px) {
    #my_card {
        width: 100%;
    }
}

@media screen and (max-width: 700px) {
    #my_card {
        font-size: .6rem;

        .title {
            font-size: 1.7rem;
            margin-bottom: 1rem;
        }
    }
}
</style>