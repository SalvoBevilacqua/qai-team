<script>
import goUp from './goUp.vue';
import theses from './dataJs/theses.js';

export default {
    data() {
        return {
            thesesList: theses,
        }
    },
    components: { goUp },
}
</script>

<template>
    <div id="my_card">
        <p class="title">Theses</p>
        <div class="body">
            <!-- LISTA Awards -->
            <h3 class="bold name_section">Here is the list of students (past and present) who have collaborated with the
                team under the co-supervision of the QAI Team Leader and have worked on a thesis in Quantum AI:</h3>
            <ul>
                <li v-for="item in thesesList">
                    <a v-if="item.link" class="high_contrast" :href="item.link"><i class="fa-solid fa-arrow-right"></i></a>
                    <i v-else class="fa-solid fa-arrow-right"></i>
                    <div>
                        <p class="bold">{{ item.student }}</p>
                        <p>{{ item.when }}</p>
                        <p class="">{{ item.title }}</p>
                        <p class="italic">{{ item.where }}</p>
                        <p>{{ item.info }}</p>
                    </div>
                </li>
            </ul>

            <div class="up">
                <goUp />
            </div>
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
            display: flex;
            gap: 1rem;
            margin-bottom: 1.5rem;

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

    .bold {
        font-weight: bold;

        * {
            font-weight: normal;
        }
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