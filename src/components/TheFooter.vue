<template>
    <footer>
        <div class="footer-top">
            <div class="container">

                <!-- contacts -->
                <div class="contacts">
                    <a class="logo" href="#">
                        <span>Nex</span>
                        <span>Gen</span>
                    </a>
                    <p>A Functional HTML Template for Corporate & Business.</p>
                    <span>
                        <i class="fas fa-phone-alt"></i>
                        +1 (305) 1234-5678
                    </span>
                    <span>
                        <i class="fas fa-envelope"></i>
                        hello@example.com
                    </span>
                    <span>
                        <i class="fas fa-map-marker-alt"></i>
                        Main Avenue, 987
                    </span>
                    <a href="#" class="button button-outline">Get in touch</a>
                </div>
                <!-- /contacts -->

                <!-- links -->
                <div>
                    <TheFooterLinksCard 
                        :title="'About'"
                        :links="aboutLinks"/>
                </div>
                <div>
                    <TheFooterLinksCard 
                        :title="'Services'"
                        :links="servicesLinks"/>
                </div>
                <div>
                    <TheFooterLinksCard 
                        :title="'Support'"
                        :links="supportLinks"/>
                </div>
                <!-- /links -->
            </div>
        </div>

        <div class="footer-bottom">
            <div class="container">
                <span>Enjoy the low price. We are tracking any intention of piracy.</span>
                <span>&copy; 2020 NEXGEN is Proudly Powered by <a href="#">Codings</a></span>
            </div>
        </div>
    </footer>
</template>

<script>

//links
import aboutLinks from '../data/links/about.js'
// import servicesLinks from '../data/links/services.js'
import supportLinks from '../data/links/support.js'

//components
import TheFooterLinksCard from './TheFooterLinksCard.vue'

export default {
    name: 'TheFooter',
    components: {
        TheFooterLinksCard
    },
    data() {
        return {
            aboutLinks,
            // servicesLinks,
            supportLinks
        }
    },
    props: {
        servicesLinks: Array
    }
}
</script>

<style lang="scss" scoped>
    @import '../assets/style/variables.scss';
    @import '../assets/style/mixins.scss';

    .footer-top {
        @include flex-center ('both');
        width: 100%;
        padding: 130px 0;
        background-color: $bg-col;

        .container {
            @include flex-wrap-between;

            & > div {
                width: calc((100% - 90px) / 4);
            }

            .contacts {
                display: flex;
                flex-direction: column;
                align-items: flex-start;
                padding-right: 15px;
                font-weight: 200;
                color: $white80;

                .logo {
                    color: $white80;

                    span {
                        font-size: 26px;

                        &:first-child {
                            border-top-left-radius: 50px;
                            border-bottom-left-radius: 50px;                    
                        }
                    }                        
                }

                i {
                    margin-right: 10px;
                }
                p {
                    padding: 30px 0;
                }
                
                span {
                    margin-bottom: 15px;
                }

                .button {
                    color: $text-col;
                    margin-top: 20px;
                }
            }
        }

    }
    
    .footer-bottom {
        @include flex-center ('cross');        
        height: 90px;
        font-size: 15px;
        font-weight: 200;
        background-color: $bg-dark-col;

        .container {
            @include flex-wrap-between;

            a{
                font-size: 17px;
                color: $brand-col;

                &:hover {
                    text-decoration: underline;
                }
            }
        }
    }
</style>