<script>
import goUp from './goUp.vue';
import work from './dataJs/projects';

export default {
    data() {
        return {
            workList: work,
        }
    },
    components: { goUp },
}
</script>

<template>
    <div id="my_card">
        <p class="title">Projects</p>
        <div class="body">
            <!-- LISTA CURRENT POSITION -->
            <ul>
                <li v-for="item in workList">
                    <a v-if="item.link" class="high_contrast" :href="item.link"><i class="fa-solid fa-arrow-right"></i></a>
                    <i v-else class="fa-solid fa-arrow-right"></i>
                    <div>
                        <p class="bold">{{ item.title }}</p>
                        <p class="italic">{{ item.bold }}</p>
                        <p>{{ item.when }}</p>
                        <p>{{ item.info }}</p>
                        <p><span>Partner: </span>{{ item.partner }}</p>
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
            margin-bottom: 1.5rem;
            display: flex;
            gap: 1rem;

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