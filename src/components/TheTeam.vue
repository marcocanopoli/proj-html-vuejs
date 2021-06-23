<template>
    <section class="team light-text">
        <div class="container">
            <div class="team">
                <SectionTitle :section-title="Title"/>
                <div class="team-cards">
                    <TheTeamCard 
                        v-for="member, index in team"
                        :key="index"
                        :member="member"/>
                </div>
            </div>
            <div class="quote">
                <h3>President Speech</h3>
                <p>Lorem ipsum dolor sit, amet consectetur adipisicing elit. Rem quibusdam nostrum corporis.</p>
                <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Perspiciatis facilis harum minima deserunt doloribus ipsum soluta odit iure facere dignissimos.</p>
                <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Illo aut cum illum error modi sed veritatis?</p>
                <span>T.Johnson</span>
                <i class="fas fa-quote-right"></i>
            </div>
        </div>
    </section>
</template>

<script>
import SectionTitle from './SectionTitle.vue';
import TheTeamCard from './TheTeamCard.vue';
import team from '../data/team-members';

export default {
    name: 'TheTeam',
    components: {
        SectionTitle,
        TheTeamCard
    },
    data() {
        return {
            Title: {
                class: 'section-light-title',
                subtitle: 'We like what we do',
                titleHTML: '<span>Team</span> of Experts',
                firstText: 'Ethics and integrity are the bases on which our professionals build their careers.<br> They are fundamentals that become daily attitudes.'
            },
            team
        }
    }
}
</script>

<style lang="scss" scoped>
    @import '../assets/style/variables.scss';
    @import '../assets/style/mixins.scss';

    .team {
        background-color: $bg-col;
    }

    .container {
        display: flex;
    }

    .team-cards {
        @include flex-wrap-between;
        padding-top: 30px;
    }

    .quote {
        position: relative;
        align-self: flex-end;
        flex-shrink: 0;
        width: 360px;
        margin-left: 90px;
        padding: 40px;
        border-radius: 5px;
        background-color: $brand-dark-col;

        & > * {
            margin-bottom: 20px;
        }

        p {
            color: $white80;
        }

        span {
            font-weight: 700;
        }

        i {
            position: absolute;
            bottom: 40px;
            right: 40px;
            transform: translateY(100%);
            font-size: 24px;
            color: $black25;
        }
    }
    
</style>