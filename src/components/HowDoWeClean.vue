<template>
<div class="demonstration">
    <div class="demo">
        <div class="demo-text">
            <h1>Как мы убираем</h1>
            <p>Клинер приезжает в назначенное время со всем необходимым и сразу приступает к делу. Вам остаётся только оценить результат.</p>
        </div>
        <img class="demo-image" src="../assets/kitchen.png" alt="">
    </div>
    <div class="side-panel">
        <div class="side-panel-content">
            <h2>Как мы убираем</h2>
            <ul class="side-panel-content-list">
                <li class="list-item kitchen">→ Кухня</li>
                <li class="list-item">Комнаты</li>
                <li class="list-item" @click="bathAnimation($event)">Ванная</li>
                <li class="list-item">Прихожая</li>
            </ul>
        </div>
    </div>

    <img class="bath-image" src="../assets/bath.png" alt="">
</div>
    
</template>

<script>
import gsap from 'gsap'
import {ScrollTrigger} from 'gsap/ScrollTrigger'
gsap.registerPlugin(ScrollTrigger)
    export default {

        data() {
            return {
                tl: gsap.timeline(),
                click: true
            }
        },

        mounted() {
            this.animation()
        },

        methods: {
            animation() {
                gsap.from('.demo-image', {y: 100, duration: 1, scrollTrigger: '.demo-image'})

                ScrollTrigger.create({
                    animation: this.tl,
                    trigger: '.demo',
                    start: 'top top',
                    end: '+=50',
                    scrub: 3,
                })

                this.tl.to('.demo-text', {y: -150, duration: 2})
                .to('.demo-image', {
                    height: "100vh",
                    width: "75vw",
                    xPercent: 15.994,
                    duration: 2
                }, "-=1")
                .fromTo('.side-panel', {xPercent: -24},{xPercent: 0, display: "block", duration: 2})

                let x = 0
                let duration = 0
                let items = document.querySelectorAll('.list-item')

                items.forEach(item => {
                    this.tl.from(item, {x: x-=20, duration: duration+=.35}, "-=1")
                })

            },

            bathAnimation(event) {
                let kitchen = document.querySelector('.kitchen')
                kitchen.style = 'font-style: normal; opacity: .7;'
                kitchen.innerHTML = 'Кухня'

                if(this.click) {
                    event.target.prepend('→ ')
                    event.target.style = "font-style: italic; opacity: 1"
                }
                this.click = false

                gsap.fromTo('.bath-image', {xPercent: 200}, {duration: 1, xPercent: 31.95, display: 'block',
                    scrollTrigger: {
                        trigger: '.bath-image',
                        toggleActions: "play none reverse none",
                        start: 'top top',
                        end: "-=200",
                    }
                })
            }
        }
    }
</script>

<style lang="scss" scoped>
    .demonstration {
        position: relative;
    }

    .demo {
        width: 80vw;
        display: flex;
        align-items: center;
        flex-direction: column;
        margin: 0 auto;
        margin-top: 149px;
        position: relative;
        &-text {
            display: flex;
            justify-content: space-between;
            margin-bottom: 52px;
            h1 {
                width: 40%;
                font-size: 44px;
                line-height: 53px;
                font-weight: 300;
            }
            p {
                width: 35%;
                font-size: 18px;
                line-height: 25px;
                font-weight: 300;
            }
        }

        &-image {
            width: 100%;
        }
    }

    .side-panel {
        height: 100vh;
        width: 25vw;
        background-color: #5A30F0;
        display: none;
        position: absolute;
        bottom: 0;

        &-content {
            position: relative;
            h2 {
                margin-top: 35px;
                margin-left: 53px;
                font-size: 16px;
                line-height: 21px;
                font-weight: 500;
                color: white;
            }

            ul {
                list-style: none;
                margin-top: 256px;
                margin-left: 60px;
                

                .list-item {
                    font-size: 44px;
                    line-height: 53px;
                    font-weight: 300;
                    opacity: .7;
                    color: white;
                }

                .list-item.kitchen {
                    opacity: 1;
                    font-style: italic;
                }

                li:not(:last-child) {
                    margin-bottom: 22px;
                }
            }
        }
    }

    .bath-image {
        position: absolute;
        bottom: 0;
        height: 100vh;
        display: none;
        width: 75vw;
    }

    @media (max-width:1220px) {
        .side-panel-content {
            ul {
                .list-item {
                    font-size: 34px;
                    line-height: 43px;
                }
            }
        }
    }

    @media (max-width: 1030px) {
        .side-panel-content {
            ul {
                .list-item {
                    font-size: 24px;
                    line-height: 33px;
                }
            }
        }
    }

    @media (max-width: 780px) {
        .side-panel-content {
            h2 {
                margin-top: 15px;
                margin-left: 33px;
                font-size: 16px;
                line-height: 21px;
                font-weight: 500;
                color: white;
            }

            ul {
                .list-item {
                    font-size: 20px;
                    line-height: 28px;
                }
            }
        }
    }

    @media (max-width: 675px) {
        .side-panel-content {
            ul {
                margin-left: 30px;
                .list-item {
                    font-size: 14px;
                    line-height: 23px;
                }
            }
        }
    }


    @media (max-width: 435px) {
        .side-panel-content {
            h2 {
                margin-top: 5px;
                margin-left: 13px;
                font-size: 12px;
                line-height: 18px;
            }
            ul {
                margin-left: 15px;
                .list-item {
                    font-size: 14px;
                    line-height: 23px;
                }
            }
        }
    }
</style>