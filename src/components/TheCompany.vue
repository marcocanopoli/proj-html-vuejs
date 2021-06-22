<template>
    <section>
        <div class="container">
            
            <div class="left">
                <SectionTitle :sectionTitle="Title"/>
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
import SectionTitle from './SectionTitle.vue'

export default {
    name: 'TheCompany',
    components: {
        SectionTitle
    },
    data() {
        return {
            Title: {
                class: 'section-light-title',
                subtitle: 'About the network',
                titleHTML: '<span>The</span> Company',
                firstText: 'Lorem, ipsum dolor sit amet consectetur adipisicing elit. Sit exercitationem sint quisquam accusamus unde, earum numquam dolores modi, inventore debitis.',
                secondText: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Officia in minus adipisci eius, pariatur et.'
            }
        }
    }
}
</script>

<style lang="scss" scoped>
    @import '../assets/style/variables.scss';
    @import '../assets/style/mixins.scss';

    section {
        background-color: $bg-col;

        .container {
            @include flex-center ('both');
            justify-content: space-between;
            height: 100%;

            .right,
            .left {
                width: calc((100% - 60px) / 2);                
            }           

            .right {
                display: flex;
                justify-content: space-between;
                align-content: space-between;
                flex-wrap: wrap;
                margin-left: 90px;

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

                    p {
                        color: $white80;
                    }
                }
            }
        }
    }

</style>