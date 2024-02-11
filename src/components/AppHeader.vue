<script>
export default {

}
</script>

<template>
    <div id="header">
        <p><span class="high_contrast">QAI Team: </span>pushing the boundaries of <span class="high_contrast">Artificial
                Intelligence</span> using <span class="high_contrast">Quantum</span> Computing!</p>
        <p>The <span class="high_contrast">QAI team </span>at DFKI Saarbruecken specializes in designing and implementing
            quantum algorithms for computationally hard AI problems.</p>
    </div>
</template>

<style scoped lang="scss">
@use "../style/variables" as *;

#header {
    margin-bottom: 4rem;
    width: 100%;
    font-size: $fontSizeHeader;
    font-weight: 400;

    p {
        width: 95%;
        margin-bottom: 1rem;
    }

    .high_contrast {
        &:hover {
            color: $colorFont;
        }
    }
}

@media screen and (max-width: 1250px) {
    #header {
        font-size: 1.5rem;
        margin-bottom: 2rem;

        p {
            margin-bottom: .5rem;
        }
    }
}
</style>