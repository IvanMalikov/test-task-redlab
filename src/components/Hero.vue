<template>
    <div class="title">
        <div class="title-inner">
            <img class="title-inner-image" src="../assets/CleaningInKyiv.png" alt="">
            <div class="title-inner-text">
                <h1>Уборка квартир в Киеве </h1>
                <p>Мы уберем у вас дома или в офисе. Наведем чистоту после ремонта и проведем генеральную уборку.</p>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        
    }
</script>

<style lang="scss" scoped>

    .title {
        font-family: "TTTravels";
        margin-bottom: 73px;
        &-inner {
            display: flex;
            align-items: center;

            &-text {
                display: flex;
                flex-direction: column;
                margin-left: 155px;
                margin-right: 164px;

                h1 {
                    font-size: 76px;
                    line-height: 84px;
                    font-weight: 300;
                    margin-bottom: 30px;
                }

                p {
                    font-weight: 300;
                    font-size: 18px;
                    line-height: 25px;

                }
            }
        }
    }

    @media (max-width: 1220px) {
        .title {

            &-inner {
                &-text {
                    margin-left: 70px;
                    margin-right: 70px;
                }
            }
            
        }
    }

    @media (max-width: 1120px) {
        .title {

            &-inner {
                &-text {
                    margin-left: 20px;
                    margin-right: 20px;
                }
            }
            
        }   
    }

    @media (max-width: 1065px) {
        .title {

            &-inner {
                position: relative;
                z-index: -1;
                img {
                    width: 100%;
                }

                &-text {
                    position: absolute;
                    color: black;
                    text-align: center;
                    h1 {
                        font-size: 100px;
                        line-height: 120px;
                        font-weight: 500;
                        margin-bottom: 30px;
                    }

                    p {
                        font-weight: 400;
                        font-size: 50px;
                        line-height: 75px;

                    }
                }

            }
            
        } 
    }

    @media (max-width: 820px) {
        .title {

            &-inner {

                &-text {
                    h1 {
                        font-size: 75px;
                        line-height: 100px;
                        font-weight: 500;
                        margin-bottom: 30px;
                    }

                    p {
                        font-weight: 400;
                        font-size: 25px;
                        line-height: 50px;

                    }
                }

            }
            
        } 
    }

    @media (max-width: 560px) {
        .title {

            &-inner {

                &-text {
                    h1 {
                        font-size: 50px;
                        line-height: 75px;
                        font-weight: 500;
                        margin-bottom: 30px;
                    }

                    p {
                        font-weight: 400;
                        font-size: 25px;
                        line-height: 50px;

                    }
                }

            }
            
        } 
    }

    @media (max-width: 460px) {
        .title {

            &-inner {

                &-text {
                    h1 {
                        font-size: 30px;
                        line-height: 40px;
                        font-weight: 500;
                        margin-bottom: 30px;
                    }

                    p {
                        font-weight: 400;
                        font-size: 20px;
                        line-height: 30px;

                    }
                }

            }
            
        } 
    }
</style>