<template>
    <header class="full-width" :class="{light: scrolling > 20, big_header: smartClass}">
        <div class="header container px-20">
            <div class="header-logo">
                <img src="@/assets/Logo.svg" alt="">
            </div>
            <nav class="header-menu">
                <ul>
                    <li class="active">
                        <div class="menu-item">
                            <a href="">Alloggi</a>
                            <div class="menu-item-line"></div>
                        </div>
                    </li>
                    <li>
                        <div class="menu-item">
                            <a href="">Esperienze</a>
                            <div class="menu-item-line"></div>
                        </div>
                    </li>
                    <li>
                        <div class="menu-item">
                            <a href="">Esperienze online</a>
                            <div class="menu-item-line"></div>
                        </div>
                    </li>
                </ul>
            </nav>
            <div class="header-button">
                <a href="">Diventa un host</a>
                <a href=""><i class="fa-solid fa-globe"></i></a>
            </div>
            <div class="header-user">
                <div class="burger">
                    <div class="line"></div>
                    <div class="line"></div>
                    <div class="line"></div>
                </div>
                <div class="account">
                    <i class="fa-solid fa-user"></i>
                </div>
            </div>

        </div>
    </header>



</template>

<script>
export default {
    name: 'TheHeader',

    props: {
        scrolling: Number,
        smartClass: Boolean,
    }
}
</script>

<style scoped lang="scss">
@import '../styles/var.scss';

header {
    background-color: black;
    position: fixed;
    height: 160px;
    z-index: 9999;
    box-shadow: 0px 0px 0px black;
    transition: all 0.3s ease;
    .header {
        height: 70px;
        display: flex;
        align-items: center;
        justify-content: space-between;
        .header-logo {
            width: 15%;
            height: 35px;

            img {
                height: 100%;
                filter: brightness(500%)
            }
        } 
        .header-menu {
            height: 100%;
            
            flex-grow: 1;
            display: flex;
            justify-content: center;
            ul {
                height: 100%;
                width: 30%;
                display: flex;
                list-style: none;
                align-items: center;
                li {
                    width: 100%;
                    margin-right: 35px;
                    .menu-item {
                        display: flex;
                        flex-direction: column;
                        white-space: nowrap;
                        justify-content: center;
                        align-items: center;
                        margin-top: 6px;
                        a {
                            text-decoration: none;
                            color: white;
                            font-weight: 300;
                        }
                        .menu-item-line {
                            height: 2px;
                            width: 2px;
                            background-color: white;
                            margin-top: 5px;
                            opacity: 0;
                            transition: width 0.5s ease;
                        }
                    }
                        &:last-child {
                            margin-right: 0;
                        }
                }
                li:hover {
                    .menu-item {
                        a {
                            opacity: 0.8;
                        }
                        .menu-item-line {
                            opacity: 1;
                            width: 4px;
                        }
                    }
                }
                li.active {
                    .menu-item {
                        .menu-item-line {
                            opacity: 1;
                            width: 15px;
                        }
                    }
                }
            }
            
        }
        .header-button {
            height: 100%;
            flex-grow: 0;
            display: flex;
            justify-content: flex-end;
            align-items: center;
            a {
                color: white;
                text-decoration: none;
                padding: 12px 15px;
                border-radius: 100px;
                cursor: pointer;
                font-size: 14px;
                font-weight: 400;
                &:hover {
                    background-color: rgba(255, 255, 255, 0.173);
                }
            }
        }
        .header-user {
            background-color: white;
            display: flex;
            align-items: center;
            padding: 8px 15px;
            border-radius: 100px;
            cursor: pointer;
            margin-left: 3px;
            border: 1px solid rgb(199, 199, 199);
            .burger {
                height: 20px;
                width: 15px;
                display: flex;
                flex-direction: column;
                justify-content: center;
                margin-right: 10px;
                .line {
                    width: 100%;
                    height: 2px;
                    background-color: #717171;
                    margin-bottom: 2px;
                    border-radius: 100px;
                    &:last-child {
                        margin-bottom: 0;
                    }
                }
            }
            .account {
                background-color: #717171;
                height: 25px;
                width: 25px;
                display: flex;
                align-items: center;
                justify-content: center;
                border-radius: 100%;
                border: 2px solid #717171;
                overflow: hidden;
                i {
                    color: white;
                    font-size: 20px;
                    position: relative;
                    top: 3px;
                }
            }
        }
    }
}

header.light {
    background-color: #fff;
    position: fixed;
    height: auto;
    box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.120);
    transition: all 0.3s ease;
    .header {
        .header-logo {
            img {
                filter: none;
            }
        }
        .header-menu {
            display: none;
        }
        .header-button {
            flex-grow: 1;
            a {
                color: $black-color;
            }
        }
    }
}

header.big_header {
    height: 160px;
    transition: all 0.3s ease;
    .header {
        .header-menu {
            display: flex;
            width: 65%;
            ul {
                li {
                    .menu-item {
                        a {
                            color: black;
                        }
                        .menu-item-line {
                            background-color: black
                        }
                    }
                }
            }
        }
    }
}

</style>