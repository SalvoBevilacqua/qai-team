<script>
export default {
}
</script>

<template>
    <div id="my_card">
        <div class="content">
            <p class="title">Members</p>
            <div class="subtitle">
                <p class="">We are part of the Intelligent Information Systems (I2S) Research Group of the
                    Agents and Simulated Reality (ASR) Department of the German Research Center for Artificial Intelligence
                    (DFKI) in Saarbruecken, located in the Saarland Informatics Campus.</p>
            </div>

            <div class="body">
                <div class="member">
                    <img src="../../img/profile/macaluso.jpg" alt="macaluso">
                    <div class="text">
                        <h3>Dr. Antonio Macaluso</h3>
                        <p class="italic">Head</p>
                        <p class="role">Senior Researcher in Quantum AI and Lecturer at Saarland University</p>
                    </div>
                </div>

                <div class="member">
                    <img src="../../img/profile/Venkatesh.jpg" alt="venkatesh">
                    <div class="text">
                        <h3>Supreeth Venkatesh</h3>
                        <p class="italic">PhD Student (RPTU Kaiserslautern)</p>
                        <p class="role">On Quantum AI for Satellite-Based EO</p>
                    </div>
                </div>

                <div class="member">
                    <img src="../../img/profile/Sinha.jpg" alt="sinha">
                    <div class="text">
                        <h3>Akash Sinha</h3>
                        <p class="italic">Master Student</p>
                        <p class="role">Hybrid quantum-classical Reinforcement Learning for Collision-Free Naviagation of
                            Self-Driving Cars</p>
                    </div>
                </div>

                <div class="member">
                    <img src="../../img/profile/Vitanov.jpg" alt="vitanov">
                    <div class="text">
                        <h3>Georgi Vitanov</h3>
                        <p class="italic">Research Assistant</p>
                        <p class="role">Quantum Algorithms for Optimizing Flexible Production Processes in Industry 4.0 </p>
                    </div>
                </div>
            </div>

            <p>Past members: Daniel Porawski (2022-2023, Research Assistant)</p>
        </div>
    </div>
</template>

<style scoped lang="scss">
@use "../../style/variables" as *;

#my_card {
    display: flex;
    justify-content: center;
    align-items: center;
    align-content: center;
    width: 70%;
    margin: 0 auto;
    height: 100%;
    font-size: medium;

    .content {
        .title {
            font-size: 3.5rem;
            margin-bottom: 3rem;
        }

        .subtitle {
            width: 45%;

            margin: 0 auto;

            p {
                text-align: left;
                font-size: large;
                margin-bottom: 3rem;
            }
        }

        .body {
            width: 100%;
            text-align: left;
            display: flex;
            flex-wrap: wrap;
            justify-content: space-between;

            .member {
                width: 48%;
                padding: 2rem;
                border: 1px solid $colorFont;
                display: flex;
                gap: 2rem;
                margin-bottom: 3rem;

                * {
                    margin-bottom: 1rem;
                }

                img {
                    width: 25%;
                    object-fit: cover;
                }
            }
        }
    }
}

@media screen and (max-width: 1400px) {
    .subtitle {
        width: 70% !important;
    }

    .member {
        width: 100% !important;

        img {
            width: unset;
            object-fit: cover;
            height: 100%;
        }
    }
}

@media screen and (max-width: 900px) {
    #my_card {
        width: 100% !important;
    }
}

@media screen and (max-width: 700px) {
    #my_card {
        font-size: .6rem !important;

        .title {
            font-size: 1.7rem !important;
            margin-bottom: 1rem !important;
        }
    }
}
</style>