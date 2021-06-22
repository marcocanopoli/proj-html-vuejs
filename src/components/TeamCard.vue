<template>
    <div class="team-member">
        <img :src="require(`../assets/img/team-${member.pic}.jpg`)" :alt="member.name + ' pic'">
        <div>
            <h3>{{ member.name }}</h3>
            <span>{{ member.jobTitle.toUpperCase() }}</span>
            <ul class="inline-list">
                <li>
                    <a :href="member.facebook">
                        <i class="fab fa-facebook-f"></i>
                    </a>
                </li>
                <li>
                    <a :href="member.twitter">
                        <i class="fab fa-twitter"></i>
                    </a>
                </li>
                <li>
                    <a :href="member.linkedin">
                        <i class="fab fa-linkedin-in"></i>
                    </a>
                </li>
            </ul>
        </div>
    </div>
</template>

<script>
export default {
    name: 'TeamCard',
    props: {
        member: Object
    }
}
</script>

<style lang="scss" scoped>
    @import '../assets/style/variables.scss';
    @import '../assets/style/mixins.scss';

    .team-member {
        display: flex;
        height: 130px;
        width: calc((100% - 50px) / 2);

        &:nth-child(-n+2) {
            margin-bottom: 50px;
        }

        img {
            height: 100%;
            margin-right: 30px;
            border-radius: 5px;
        }

        & > div {
            display: flex;
            flex-direction: column;
            justify-content: space-between;

            h3 {
                padding-top: 5px;
            }
            span {
                font-size: 15px;
                color: $white80;
            }

            ul {
                padding-top: 10px;

                li {                
                    height: 40px;
                    width: 40px;
                    margin-right: 5px;
                    border-radius: 50%;
                    background-color: $brand-dark15-col;
                    
                    a {
                        @include flex-center ('both');
                        height: 100%;
                        width: 100%;
                        text-decoration: none;

                        i {
                            font-size: 18px;
                            color: $brand-dark-col;
                        }
                    }
                }
            }
        }

    }
</style>