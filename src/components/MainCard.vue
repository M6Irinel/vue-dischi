<template>
    <div class="container">
        <div class="flex row">
            <div v-for="(el, i) in music" :key="i" class="my-col">
                <img :src="el.poster" :alt="el.author">
                <h2> {{el.title}} </h2>
                <div class="author">
                    <h3> {{el.author}} </h3>
                    <h4> {{el.year}} </h4>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'MianCard',
    props: {
        music: Array
    }
}
</script>

<style scoped lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Lato:wght@700&display=swap');

.container {
    margin-top: 5rem;
    padding: 3rem 5rem;

    .row {
        gap: 20px 30px;
    }

    .my-col {
        flex-basis: calc(100% / 6);
        overflow: hidden;
        background-color: #2e3a46;
        padding: 15px;
        text-align: center;
        transition: transform 0.2s ease-in-out, border-radius 0.2s ease-in-out;
        
        &:hover {
            transform: scale(1.05);
            border-radius: 5px;

            img {
                transform: scale(1.05);
            }
        }
        
        img {
            transition: transform 0.2s ease-in-out;
            width: 100%;
        }
        
        h2 {
            color: #fff;
            text-transform: uppercase;
            font-size: 1.5rem;
            padding-top: 15px;
        }
        
        .author {
            padding-top: 10px;
            margin-bottom: -5px;

            h3, h4 {
                color: #897f78;
                font-size: 1rem;
            }

            h4 {
                margin-top: -8px;
                font-family: 'Lato', sans-serif;
            }
        }
    }
}
</style>