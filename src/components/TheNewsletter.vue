<template>
    <section class="light-text">
        <div class="container">
            <SectionTitle :sectionTitle="Title"/>
            <form>
                <input type="text" placeholder="Name">
                <input type="text" placeholder="Email">                
                <a href="#" class="btn btn-solid">Subscribe</a>
            </form>
        </div>
    </section>
</template>

<script>
import SectionTitle from './SectionTitle.vue';

export default {
    name: 'TheNewsletter',
    components: {
        SectionTitle
    },
    data() {
        return {
            Title: {
                class: 'section-light-title',
                subtitle: 'Newsletter',
                titleHTML: '<span>Know</span> First',
                firstText: 'Follow closely and receive content about our company and the news of the current market.'
            }
        }
    }
}
</script>

<style lang="scss" scoped>
    @import '../assets/style/variables.scss';

    section {
        background: url('../assets/img/bg-1.jpg') fixed center;

        .container {
            display: flex;
            width: 50%;

            & > div {
                padding-right: 20px;
                width: 50%;
            }

            form {
                display: flex;
                flex-direction: column;
                width: 50%;
                padding-left: 20px;

                & > * {
                    margin-bottom: 20px;
                }

                input {
                    background-color: $white50;

                    &:hover,
                    &:focus {
                        background-color: $white60;
                    }
                }

                a {
                    align-self: flex-start;
                }
            }
        }
    }
</style>