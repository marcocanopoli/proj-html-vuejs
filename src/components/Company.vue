<template>
    <section>
        <div class="container">
            
            <div class="left">
                <h5>About the network</h5>
                <h2><span>The</span> Company</h2>
                <p>Lorem, ipsum dolor sit amet consectetur adipisicing elit. Sit exercitationem sint quisquam accusamus unde, earum numquam dolores modi, inventore debitis.</p>
                <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Officia in minus adipisci eius, pariatur et.</p>
            </div>

            <div class="right">
                <div>
                    <i class="fas fa-award"></i>
                    <h3>Tradition</h3>
                    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit.</p>
                </div>
                <div>
                    <i class="fas fa-lock"></i>
                    <h3>Security</h3>
                    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit.</p>
                </div>
                <div>
                    <i class="fas fa-edit"></i>
                    <h3>Certificate</h3>
                    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit.</p>
                </div>
                <div>
                    <i class="fas fa-graduation-cap"></i>
                    <h3>Expertise</h3>
                    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit.</p>
                </div>
            </div>
        </div>
    </section>
</template>

<script>
export default {
    name: 'Company'
}
</script>

<style lang="scss" scoped>
    @import '../assets/style/variables.scss';
    @import '../assets/style/mixins.scss';

    section {
        padding: 130px 0;
        background-color: $bg-col;

        .container {
            @include flex-center ('both');
            justify-content: space-between;
            height: 100%;

            .right,
            .left {
                width: calc((100% - 60px) / 2);
            }

            .left {
                & > * {
                    margin-bottom: 20px;
                }
            }

            .right {
                display: flex;
                justify-content: space-between;
                align-content: space-between;
                flex-wrap: wrap;

                & > div {
                    width: calc((100% - 30px) / 2);
                    
                    &:nth-child(-n+2) {
                        margin-bottom: 60px;
                    }

                    i {
                        font-size: 26px;
                        color: $brand-col;
                        margin-right: 10px;
                    }
    
                    h3 {
                        display: inline-block;
                        margin-bottom: 15px;
                    }
                }
            }
        }
    }

</style>