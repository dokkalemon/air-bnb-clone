<template>
    <section class="booking full-width" :class="{active: scrolling > 20}">
        <div class="booking-container container px-20">
            <div class="booking-input">


                <Place :openPlace="openPlaceProp"/>

        
                <button class="input-cont place" @click="openPlaceFunction" @blur="(openPlaceProp = false, openSearch = false)" v-show="scrolling < 20">
                    <span>Dove</span>
                    <p>Dove vuoi andare?</p>
                </button>
                <div class="line" v-show="scrolling < 20"></div>
                <div class="input-cont guests" v-show="scrolling < 20">
                    <span>Check-in</span>
                    <p>Aggiungi date</p>
                </div>
                <div class="line" v-show="scrolling < 20"></div>
                <div class="input-cont guests" v-show="scrolling < 20">
                    <span>Check-out</span>
                    <p>Aggiungi date</p>
                </div>
                <div class="line" v-show="scrolling < 20"></div>
                <div class="input-cont guests" v-show="scrolling < 20">
                    <span>Ospiti</span>
                    <p>Aggiungi Ospiti</p>
                </div>
                <div class="scroll-controll" v-show="scrolling > 20" >
                    <span>Inizia la ricerca</span>
                </div>
                <div class="button" :class="{active: openSearch}">
                    <i class="fa-solid fa-magnifying-glass"></i>
                    <span v-show="openSearch">Cerca</span>
                </div>

            </div>
        </div>
        
    </section>
</template>

<script>
/* import Datepicker from 'vue3-date-time-picker';
import 'vue3-date-time-picker/dist/main.css' */
import Place from '@/components/Place';


export default {
    name: 'TheBooking',
    components: {
        /* Datepicker, */
        Place,
    },
    props: {
        scrolling: Number,
    },
    data() {
        return {
            date: null,
            openPlaceProp: false,
            openSearch: false,
        }
    },

    methods: {
        openPlaceFunction() {
            if (this.openPlaceProp === false) {
                this.openPlaceProp = true;
                this.openSearch = true
            } else {
                this.openPlaceProp = false
                this.openSearch = false
            }
        }
    }
}
</script>

<style scoped lang="scss">
@import '@/styles/var';
/* @import 'vue3-date-time-picker/src/Vue3DatePicker/style/main.scss'; */


.booking {
    
    position: absolute;
    transition: all 0.3s ease;
    top: 70px;
    transition: top 0.3s ease;
    .booking-container {
        height: 85px;
        display: flex;
        justify-content: center;
        align-items: center;
        .booking-input {
            height: 65px;
            background-color: white;
            width: 850px;
            border-radius: 100px;
            display: flex;
            align-items: center;
            box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.212);
            border: 1px solid rgb(199, 199, 199);
            transition: all 0.3s ease;
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
                border: none;
                background-color: transparent;
                text-align: left;
                
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
                background-image: linear-gradient(to right, #E61E4D 0%, #E31C5F 50%, #D70466 100%);
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
            .button.active {
                width: 120px;
                span {
                    color: white;
                    font-size: 16px;
                    margin-left: 10px;
                }
            }
            .scroll-controll {
                width: 85%;
                padding: 20px 20px;
                transition: all 0.3s ease;
                span {
                    font-size: 14px;
                }
            }
        }
    }
}
.booking.active {
    background-color: transparent;
    position: fixed;
    top: 0px;
    .booking-container {
        height: 70px;
        .booking-input {
            height: 48px;
            width: 300px;
            .button {
                height: 65%;
                width: 30px;
                i {
                    font-size: 13px;
                }
            }
        }
    }
}

</style>