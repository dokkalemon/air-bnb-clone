<template>
    <section class="booking full-width">
        <div class="booking-container container px-20">
            <div class="booking-input">
                <div class="input-cont place">
                    <span>Dove</span>
                    <p>Dove vuoi andare?</p>
                </div>
                <div class="line"></div>
                <div class="input-cont guests">
                    <span>Check-in</span>
                    <p>Aggiungi date</p>
                </div>
                <div class="line"></div>
                <div class="input-cont guests">
                    <span>Check-out</span>
                    <p>Aggiungi date</p>
                </div>
                <div class="line"></div>
                <div class="input-cont guests">
                    <span>Ospiti</span>
                    <p>Aggiungi Ospiti</p>
                </div>
                <div class="button">
                    <i class="fa-solid fa-magnifying-glass"></i>
                </div>




            </div>
        </div>
    </section>
</template>

<script>
/* import Datepicker from 'vue3-date-time-picker';
import 'vue3-date-time-picker/dist/main.css' */


export default {
    name: 'TheBooking',
    components: {
        /* Datepicker, */
    },
    data() {
        return {
            date: null,
        }
    }
}
</script>

<style scoped lang="scss">
@import '@/styles/var';
/* @import 'vue3-date-time-picker/src/Vue3DatePicker/style/main.scss'; */


.booking {
    background-color: black;
    position: fixed;
    margin-top: 70px;
    .booking-container {
        height: 85px;
        display: flex;
        justify-content: center;
        align-items: center;
        .booking-input {
            height: 65px;
            background-color: white;
            width: 57%;
            border-radius: 100px;
            display: flex;
            align-items: center;
            position: relative;
            .input-cont {
                height: 100%;
                width:23.3333%;
                border-radius: 100px;
                padding: 0px 20px;
                display: flex;
                flex-direction: column;
                justify-content: center;
                cursor: pointer;
                position: relative;
                
                span {
                    font-size: 12px;
                    font-weight: 600;
                    color: $black-color;
                }
                p {
                    font-size: 14px;
                    font-weight: 300;
                    color: $black-color;
                    margin-top: 3px;
                }
            &:hover {
                background-color: $secondary-color;
            }
            }
            .place {
                width: 30%;
            }
            .line {
                height: 50%;
                width: 1px;
                background-color: rgb(199, 199, 199);
            }
            .button {
                height: 75%;
                width: 52px;
                background-color: $primary-color;
                border-radius: 100px;
                display: flex;
                align-items: center;
                justify-content: center;
                margin-right: 10px;
                transition: all 0.2s ease;
                cursor: pointer;
                i {
                    color: white;
                }
            &:hover {
                background-color: #dc0e63;
            }
            }
        }
    }
}

</style>