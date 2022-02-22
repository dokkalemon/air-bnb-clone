<template>
    <section class="jumbo full-size" :class="{active: scrolling > 20}">
        <div class="jumbo-container container px-20">
            <div class="image">
                <img src="@/assets/Jumbo.jpg" alt="">
            </div>

        </div>
    </section>
</template>

<script>
export default {
    name: 'TheJumbotron',
    props: {
        scrolling: Number,
    }
}
</script>

<style scoped lang="scss">
.jumbo {
    background-color: black;
    padding-bottom: 100px;
    .jumbo-container {
        height: 100vh;
        position: relative;
        .image {
            height: 100%;
            width: 100%;
            position: relative;
            top: 0;
            border-radius: 15px;
            overflow: hidden;
            img {
                height: 100%;
                width: 100%;
                object-fit: cover;
                filter: brightness(40%)
            }
        }
    }

}

.jumbo.active {
    padding-top: 170px;


}

</style>