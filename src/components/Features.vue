<template>
    <div class="features">
        <div class="feature">
            <p class="description">Тщательно отобранный персонал</p>
            <img class="worker" src="../assets/worker.png" alt="">
        </div>
        <div class="feature">
            <p class="description">Качественная эко-химия</p>
            <img class="chemicals" src="../assets/chemicals.png" alt="">
        </div>
        <div class="feature">
            <p class="description">Контролируем качество</p>
            <img class="quality" src="../assets/quality.png" alt="">
        </div>
        <div class="feature">
            <p class="description">Работаем круглосуточно</p>
            <img class="round-the-clock" src="../assets/round-the-clock.png" alt="">
        </div>
    </div>
</template>

<script>
import gsap from 'gsap'
import {ScrollTrigger} from 'gsap/ScrollTrigger'
gsap.registerPlugin(ScrollTrigger)
    export default {
        mounted() {
            this.animationFeatures()
        },

        methods: {
            animationFeatures() {
                var features = gsap.utils.toArray('.feature')
                let y = 0
                let duration = 0
                features.forEach(feature => {
                    gsap.fromTo(feature, {y: y+=25},{
                        y: 0,
                        duration: duration += .35,
                        scrollTrigger: {
                            trigger: features,
                            toggleActions: "restart none none none",
                        }
                    })
                })
            }
        }
    }
</script>

<style lang="scss" scoped>
    .features {
        font-family: "TTTravels";
        margin: 0px 60px 0px 60px;
        display: flex;
        justify-content: space-between;
        flex-wrap: wrap;
        align-items: center;

        .feature {
            background-color: #F3F6FB;
            width: 300px;
            height: 328px;
            border-radius: 8px;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 20px;
            p {
                width: 219px;
                text-align: center;
                font-size: 24px;
                line-height: 31px;
                margin-top: 20px;
            }

            .worker {
                width: 151px;
                height: 151px;
            }

            .chemicals {
                width: 188px;
                height: 154px;
            }

            .quality {
                width: 211px;
                height: 174px;
            }

            .round-the-clock {
                width: 201px;
                height: 141px;
            }
        }
    }

    @media (max-width: 1320px) {
        .features {
            justify-content: center;

            .feature {
                margin-right: 10px;
            }
        }
    }
</style>