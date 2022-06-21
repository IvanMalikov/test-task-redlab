<template>
    <header class="header">
        <div class="header-inner">
            <div class="header-inner-title">
                <img src="../assets/Logo.png" alt="">
            </div>
            <div class="header-inner-button">
                <label class="switch btn-color-mode-switch">
                    <input type="checkbox" name="color_mode" id="color_mode" value="1">
                    <label for="color_mode" data-on="Офис" data-off="Дом" class="btn-color-mode-switch-inner"></label>
                </label>
            </div>
            <div class="header-inner-menu">
                <ul>
                    <li>После ремонта</li>
                    <li>Генеральная уборка</li>
                    <li>Регулярная уборка</li>
                    <li>Мойка окон</li>
                </ul>
            </div>
            <div class="header-inner-contacts">
                <div class="contacts-phone">+380 67 401 69 77</div>
                <div class="contacts-time">24/7</div>
            </div>
            <div class="header-inner-burger" @click="toggleMenu">
                <img src="../assets/burger.png" alt="">
            </div>
        </div>
    </header>
</template>

<script>
    export default {
        methods: {
            toggleMenu() {
                document.querySelector('.header-inner-menu').classList.toggle('active')
            }
        }
    }
</script>

<style lang="scss" scoped>
    .header {
        width: 100%;
        font-family: "TTTravels";
        height: 70px;
        position: absolute;
        top: 0;
        background: transparent;
        display: flex;
        align-items: center;
        &-inner {
            width: 100%;
            display: flex;
            justify-content: space-between;
            align-items: center;
            &-title {
                margin-left: 54px;
            }
            &-button {
                label {
                    font-size: 14px;
                    line-height: 15px;
                    text-align: center;
                    color: white;
                    font-weight: 500;
                }

                .btn-color-mode-switch{
                    display: inline-block;
                    margin: 0px;
                    position: relative;
                }

                .btn-color-mode-switch > label.btn-color-mode-switch-inner{
                    margin: 0px;
                    width: 131px;
                    height: 37px;
                    background: #fff;
                    border: 1px solid #E2E8F0;
                    border-radius: 48px;
                    overflow: hidden;
                    position: relative;
                    transition: all 0.3s ease;
                    display: block;
                }

                .btn-color-mode-switch > label.btn-color-mode-switch-inner:before{
                    content: attr(data-on);
                    position: absolute;
                    font-size: 13px;
                    font-weight: 500;
                    top: 10px;
                    right: 13px;
                    font-size: 14px;
                    line-height: 15px;
                    color: #636C81;
                }

                .btn-color-mode-switch > label.btn-color-mode-switch-inner:after{
                    content: attr(data-off);
                    width: 55px;
                    height: 31px;
                    background: #5A30F0;
                    border-radius: 34px;
                    position: absolute;
                    left: 3px;
                    top: 3.7px;
                    transition: all 0.3s ease;
                    box-shadow: 0px 0px 6px -2px #111;
                }

                .btn-color-mode-switch input[type="checkbox"]{
                    cursor: pointer;
                    width: 55px;
                    height: 31px;
                    opacity: 0;
                    position: absolute;
                    top: 0;
                    z-index: 1;
                    margin: 0px;
                }

                .btn-color-mode-switch input[type="checkbox"]:checked + label.btn-color-mode-switch-inner{
                    background: #151515;
                    color: #fff;
                }

                .btn-color-mode-switch input[type="checkbox"]:checked + label.btn-color-mode-switch-inner:after{
                    content: attr(data-on);
                    left: 72px;
                    background: #5A30F0;
                }

                .btn-color-mode-switch input[type="checkbox"]:checked + label.btn-color-mode-switch-inner:before{
                    content: attr(data-off);
                    right: auto;
                    left: 20px;
                }

                .btn-color-mode-switch input[type="checkbox"]:checked + label.btn-color-mode-switch-inner{
                    background: white;
                    color: #fff;
                }
            }
            &-menu {
                ul {
                    list-style: none;
                    display: flex;
                    li:not(:last-child) {
                        margin-right: 32px;
                    }
                }
            }
            &-contacts {
                display: flex;
                font-size: 16px;
                line-height: 19px;
                font-weight: 500;
                .contacts-phone {
                    border-right: 1.5px solid black;
                    padding-right: 15px;
                    margin-right: 15px;
                }
            }
            &-burger {
                margin-right: 30px;
            }
        }
    }

    @media (max-width: 1260px) {
        .header-inner-menu {
            transition: all .5s;
            transform: translateY(-150%);
            position: absolute;
            top: 0;
            right: 0;
            left: 0;
            background-color: #5A30F0;
            color: white;
            padding-top: 30px;
            padding-bottom: 30px;
            text-align: center;
            ul {
                flex-direction: column;
                li:not(:last-child) {
                    margin-right: 0;
                    margin-bottom: 10px;
                }
            }
        }

        .header-inner-menu.active {
            transform: translateY(0);
        }

        .header-inner-burger {
            z-index: 20;
        }
    }

    @media (max-width: 620px) {
        .header-inner-title {
            margin-left: 10px;
        }
        .header-inner-contacts {
            .contacts-phone {
                font-size: 9px;
                line-height: 15px;
                font-weight: 300;
                border-right: none;
                padding-right: 0;
                margin-right: 0;
            }
            .contacts-time {
                display: none;
            }
        }

        .header-inner-burger {
            margin-right: 10px;
        }
    }
</style>