<script>
import goUp from './goUp.vue';
import coll from './dataJs/collaborations';

export default {
    data() {
        return {
            collList: coll,
        }
    },
    components: { goUp },
}
</script>

<template>
    <div id="my_card">
        <p class="title">Collaborations</p>
        <div class="body">
            <h3 class="bold name_section">All current collaborations of the QAI Team with international institutions:</h3>
            <ul>
                <li v-for="item in collList">
                    <a v-if="item.link" class="high_contrast" :href="item.link"><i class="fa-solid fa-arrow-right"></i></a>
                    <i v-else class="fa-solid fa-arrow-right"></i>
                    <div>
                        <p class="high_contrast">{{ item.name }}</p>
                        <p class="italic">{{ item.infoItalic }}</p>
                        <p>{{ item.info }}</p>
                    </div>
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

    i {
        &:hover {
            color: $colorFont;
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