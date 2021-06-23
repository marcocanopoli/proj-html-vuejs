<template>
    <header class="page-header">
        <!-- top bar -->
        <div class="top-bar">
            <ul class="container">
                <li v-for="contact, index in contactsLinks"
                    :key="index">                        
                    <a :href="contact.url">
                        <i :class="contact.icon"></i>
                        <span>{{ contact.text }}</span>
                    </a>
                </li>                
            </ul>
        </div>
        <!-- /top bar -->

        <!-- menu -->
        <nav class="menu container">
            <a class="logo" href="#">
                <span>Nex</span>
                <span>Gen</span>
            </a>
            <ul :class="menuClass">
                <li>
                    <a  href="javascript:void(0);" 
                        id="hamburger-icon" 
                        @click="openMenu()">
                        <i class="fa fa-bars"></i>
                    </a>
                </li>
                <li v-for="link, index in menuLinks"
                    :key="index">
                    <a :href="link.url">{{ link.text.toUpperCase() }}</a>
                </li>
                <li id="menu-button">
                    <a class="button button-solid" href="#">Get in touch</a>
                </li>
            </ul>
        </nav>
        <!-- /menu -->

        <!-- hero -->
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
                    <a href="#" class="button button-solid">Get in touch</a>
                    <a href="#" class="button button-outline">Read more</a>
                </form>
            </div>
        </div>
        <!-- /hero -->
    </header>
</template>

<script>
import menuLinks from '../data/links/menu.js';
import contactsLinks from '../data/links/contacts.js';

export default {
    name: 'TheHeader',
    data() {
        return {
            menuLinks,
            contactsLinks,
            menuClass: ''
        }
    },
    methods: {
        openMenu() {
            if (this.menuClass == '') {
                this.menuClass = 'responsive';
            } else {
                this.menuClass = '';
            }
        }
    }
}
</script>

<style lang="scss" scoped>
    @import '../assets/style/variables.scss';
    @import '../assets/style/mixins.scss';

    .page-header {
        display: flex;
        flex-direction: column;
        height: 100vh;
        background: url('../assets/img/bg-6.jpg') fixed 0% 30%;
        
        .top-bar {
            @include flex-center ('cross');
            flex-shrink: 0;
            height: 50px;
            font-weight: 300;
            background-color: $text-dark-col;

            ul {
                display: flex;
                justify-content: space-between;
                font-size: 14px;

                li {
                    display: inline-block;

                    &:first-child {
                        flex-grow: 1;
                    }
                    &:not(:first-child) {
                        margin-left: 30px;
                    }                    

                    * {
                        color: $white70;
                    }

                    i {
                        margin-right: 5px;
                        transition: $trans-time;
                    }

                    a {
                        transition: $trans-time;
                        &:hover {
                            &, i {
                                color: $brand-col;                                
                            }
                        }
                    }
                }
            }
        }
        
        .menu {
            @include flex-center ('cross');
            justify-content: space-between;
            flex-shrink: 0;
            height: 70px;
            margin-top: 10px;

            #hamburger-icon {
                display: none;
            }

            a:not(.button) {
                color: $text-dark-col;
                transition: $trans-time;
                
                &:hover:not(.logo) {
                    color: $brand-col;
                    transform: translateY(-4px);
                }
            }

            ul {
                li {
                    display: inline-block;
                    margin-left: 40px;
                    font-size: 17px;
                    font-weight: 500;

                    &:first-child {
                        margin-left: 0;
                    }

                    a {
                        display: inline-block;
                    }
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
                    color: $text-dark-col;
                }

                h4 {
                    margin-bottom: 10px;                    
                }

                form {
                    display: flex;
                    flex-wrap: wrap;
                    width: 100%;
                    margin-top: 30px;
                    
                    input,
                    .select-box {
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

    //width media queries    
    @media screen and (max-width: 1599px){

        .page-header {
            background-position: 80% 0%;

            .container {
                width: 70%;
            }
            #menu-button {
                display: none;
            }       
    
            .hero {
                justify-content: center;
                text-align: center;
            }
        }
    }

    @media screen and (max-width: 1399px){
        .page-header {
    
            .hero {
                div {
                    width: 55%;
                }                
            }
        }
    }

    @media screen and (max-width: 1199px){
        .page-header {
            background-position: 70% 0%;
            .container {
                width: 80%;
            }
        }
    }

    @media screen and (max-width: 991px){
        .page-header {
            .top-bar{
                ul {
                    li {
                        &:first-child {
                            flex-grow: 0;
                        }
                        &:nth-child(3) {
                            flex-grow: 1;
                        }
                        span {
                            display: none;
                        }
                    }
                }
            }
            
            .hero {
                div {
                    width: 70%;

                    h1 {
                        font-size: 64px;
                        line-height: 70px;
                    }
                    .button {
                        width: calc(50% - 15px);
                    }
                } 

            }
        }
    }

    @media screen and (max-width: 767px){
        .page-header {
            background-position: 60% 0%;
            .menu {
                height: unset;
                padding-top: 20px;
                align-items: flex-start;

                ul {
                    li:not(:first-child){
                        display: none;          
                    }

                    #hamburger-icon {
                        display: block;

                        &:hover {
                            transform: none;
                        }
                    }

                    &.responsive {

                        li {
                            display: block;
                            text-align: right; 
                            margin: 0;
                        }
                    }
                }
            }

            .hero {
                position: relative;

                div:not(.select-box) {

                    @include absolute-center;
                    width: 60%;

                    h1 {
                        font-size: 54px;
                    }                
    
                    .button {
                        width: 100%;
                        margin-bottom: 15px;
                    }
                }
            }
        }
    }

    @media screen and (max-width: 575px){
        .page-header {
            .menu {
                ul {
                    z-index: 1;

                    li:not(:first-child) {
                        padding: 2px 10px 2px 20px;
                        background-color: $text-dark-col;
                        a {                        
                            color: $text-col;
                        }                
                    }

                    li:nth-child(2) {
                        padding-top: 10px;
                        border-top-left-radius: 10px;
                        border-top: 3px solid $brand-col;
                    }
                    li:nth-last-child(2) {
                        padding-bottom: 10px;
                        border-bottom-left-radius: 10px;
                        border-bottom-right-radius: 10px;
                        border-bottom: 3px solid $brand-col;
                    }
                }
            }

            .hero {

                div:not(.select-box) {
                    width: 80%;

                    form {
                        input,
                        .select-box,
                        .button {
                            width: 100%;
                            margin-right: 0;
                            margin-left: 0;
                        }
                    }
                }
            }
        }
    }

    @media screen and (max-width: 450px){
        .page-header {
            .hero {
                div:not(.select-box) {

                    h1 {
                        font-size: 34px;
                        line-height: 50px;
                    }
                }
            }
        }
    }

    //height media queries
    @media screen and (max-width: 575px) and (max-height: 800px) {
        .page-header {
            .hero {
                margin-top: 30px;
                margin-bottom: 30px;
                div:not(.select-box) {
                    overflow-y: scroll;
                    height: 100%;
                }
            }
        }
    }

</style>