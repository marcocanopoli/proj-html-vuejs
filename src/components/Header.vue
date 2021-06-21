<template>
    <header>
        <!-- top bar -->
        <div class="top-bar">
            <ul class="container inline-list">
                <li v-for="contact, index in contactsLinks"
                    :key="index">                        
                    <a :href="contact.url">
                        <i :class="contact.icon"></i>
                        {{ contact.text }}
                    </a>
                </li>
            </ul>
        </div>
        <!-- /top bar -->

        <!-- menu -->
        <nav class="container">
            <a class="logo" href="#">
                <span>Nex</span>
                <span>Gen</span>
            </a>
            <ul class="inline-list">
                <li v-for="link, index in headerLinks"
                    :key="index">
                    <a :href="link.url">{{ link.text.toUpperCase() }}</a>
                </li>
                <li>
                    <a class="btn btn-solid" href="#">Get in touch</a>
                </li>
            </ul>
        </nav>
        <!-- /menu -->

        <div class="hero">
            <h5>Fusions & acquisitions</h5>
            <h1>Insurance consulting</h1>
            <form action="">

            </form>
        </div>

    </header>
</template>

<script>
import headerLinks from '../data/header-links.js';
import contactsLinks from '../data/contacts-links.js';

export default {
    name: 'Header',
    data() {
        return {
            headerLinks,
            contactsLinks
        }
    }
}
</script>

<style lang="scss" scoped>
    @import '../assets/style/variables.scss';
    @import '../assets/style/mixins.scss';

    header {
        
        a {
            text-decoration: none;                        
        }

        .top-bar {
            @include flex-center ('cross');
            height: 50px;
            background-color: $text-dark-col;
            font-weight: 300;

            ul {
                display: flex;
                justify-content: space-between;
                font-size: 14px;
                color: $text-light-col;

                li {
                    &:first-child {
                        flex-grow: 1;
                    }
                    &:not(:first-child) {
                        margin-left: 30px;
                    }

                    * {
                        color: $text-light-col;
                    }

                    i {
                        margin-right: 5px;
                    }
                }
            }
        }
        
        nav {
            @include flex-center ('cross');
            justify-content: space-between;
            height: 90px;

            *:not(.btn) {
                color: $text-dark-col;
                
            }

            a {
                font-size: 18px;

                span {
                    font-size: 20px;
                    font-weight: 600;
                    text-transform: uppercase;
                    letter-spacing: 5px;
                    margin-right: 5px;

                    &:first-child {
                        padding: 10px 0 10px 30px;
                        border-top-left-radius: 25px;
                        border-bottom-left-radius: 25px;
                        color: $brand-col;
                        background-color: $brand-alpha20-col;
                    }
                }
            }

            ul {
                li {
                    margin-left: 40px;
                }
            }
        }
    }
    
</style>