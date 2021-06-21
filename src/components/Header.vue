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

        <div class="container hero">
            <div>
                <h4>Fusions & acquisitions</h4>
                <h1>Insurance consulting</h1>
                <form>
                    <input type="text" placeholder="Name">
                    <input type="text" placeholder="Email">
                    <input type="text" placeholder="Phone">
                    <div class="select-box">
                        <select name="more-info" id="more-info">
                            <option value="">More Info</option>    
                        </select>
                    </div>
                    <a href="#" class="btn btn-solid">Get in touch</a>
                    <a href="#" class="btn btn-outline">Read more</a>
                </form>
            </div>
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
        height: 100vh;
        display: flex;
        flex-direction: column;
        background: url('../assets/img/bg-6.jpg') 0% 30%;
        
        a {
            text-decoration: none;                        
        }

        .top-bar {
            @include flex-center ('cross');
            flex-shrink: 0;
            height: $topbar-height;
            background-color: $text-dark-col;
            font-weight: 300;

            ul {
                display: flex;
                justify-content: space-between;
                font-size: 14px;
                color: $white60;

                li {
                    &:first-child {
                        flex-grow: 1;
                    }
                    &:not(:first-child) {
                        margin-left: 30px;
                    }

                    * {
                        color: $white60;
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
            flex-shrink: 0;
            height: $nav-height;
            margin-top: 10px;

            a:not(.btn) {
                color: $text-dark-col;                
            }

            ul {
                li {
                    margin-left: 40px;
                }
            }
        }

        .hero {
            @include flex-center ('cross');
            justify-content: flex-end;            
            height: 100%;

            div {
                width: 45%;

                h1 {
                    margin: 0;
                    text-transform: capitalize;
                    font-size: 74px;
                    font-weight: 900;
                    line-height: 86px;
                    color: $text-dark-col;
                }

                h4 {
                    margin-bottom: 10px;
                    text-transform: uppercase;
                    font-size: 18px;
                    font-weight: 500;
                    color: $brand-col;
                }

                form {
                    display: flex;
                    flex-wrap: wrap;
                    width: 100%;
                    margin-top: 30px;
                    
                    input,
                    .select-box {
                        display: inline-block;
                        width: calc(50% - 15px);
                        margin: 0 15px 15px 0;
                    }

                    select {
                        height: 100%;
                        width: 100%;
                    }                    

                    a {
                        margin-right: 15px;
                    }
                }
            }
        }
    }
    
</style>