<script>
import goUp from './goUp.vue';
import teachlist from './dataJs/teaching.js';

export default {
    data() {
        return {
            list: teachlist,
        }
    },
    components: { goUp },
}
</script>

<template>
    <div id="my_card">
        <p class="title">Teaching</p>
        <div class="body">
            <!-- LISTA GENERALE -->
            <ul>
                <li v-for="item in list">
                    <a v-if="item.link" class="high_contrast" :href="item.link"><i class="fa-solid fa-arrow-right"></i></a>
                    <i v-else class="fa-solid fa-arrow-right"></i>
                    <div>
                        <p class="bold">{{ item.textLink }}</p>
                        <p>{{ item.when }}</p>
                        <p class="sub">{{ item.where }}</p>
                        <p>{{ item.info }}</p>
                        <p v-if="item.infoTwo">{{ item.infoTwo }}</p>
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
                margin-bottom: .5rem;
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

    .sub {
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