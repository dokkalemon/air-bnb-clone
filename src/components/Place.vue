<template>
    <section class="place" v-show="openPlace">
        <span>VAI DOVE VUOI, QUANDO VUOI</span>
        <div class="button">
            <span>Sono flessibile</span>
            <i class="fa-solid fa-angle-right"></i>
        </div>
    </section>
</template>

<script>
export default {
    name: 'ThePlace',
    props: {
        openPlace: Boolean,
    }
}
</script>

<style scoped lang="scss">
.place {
    position: absolute;
    height: 160px;
    width: 500px;
    background-color: white;
    border-radius: 30px;
    top: 85px;
    box-shadow: 0px 10px 20px rgba(0, 0, 0, 0.200);
    padding: 35px;
    span {
        font-size: 12px;
        font-weight: 600;
    }
    .button {
        height: 60px;
        border-radius: 100px;
        box-shadow: 0px 5px 15px rgba(0, 0, 0, 0.150);
        display: flex;
        justify-content: space-between;
        align-items: center;
        padding: 0px 20px;
        margin-top: 20px;
        border: 1px solid rgb(199, 199, 199);
        cursor: pointer;
        span {
            font-size: 18px;
            color: #74019a;
            font-weight: 500;
        }
        i {
            font-size: 30px;
            color: #74019a;
        }
    &:hover {
        box-shadow: 0px 0px 20px rgba(0, 0, 0, 0.180);

    }
    }
}

</style>