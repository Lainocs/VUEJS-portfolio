<template>
    <div class="content">
        <h2>Skills</h2>
        <div class="card">
            <Splide :options="{ rewind: true, autoplay: true, width: '70vw' }">
                <SplideSlide v-for="skill in skills" :key="skill" class="tab">
                    <img :src="skill.skillPicture" alt="skill-logo">
                    <div class="skill">
                        <h3 class="skill-title">{{skill.skillName}}</h3>
                        <div class="skill-content">
                            <div class="left">
                                <div class="typewriter">
                                    <h3>{{skill.skillCode}}</h3>
                                </div>
                            </div>
                        </div>
                    </div>
                </SplideSlide>
            </Splide>
        </div>
        <div class="card">
            <div class="otherSkills">
                <h3>Autres compétences</h3>
                <div class="otherSkills-content">
                    <div v-for="otherSkill in otherSkills" :key="otherSkill" class="left others">
                        <img :src="otherSkill.skillPicture">
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import '@splidejs/splide/dist/css/splide.min.css';
import { Splide, SplideSlide } from '@splidejs/vue-splide';
    export default {
    name: "Skills",
    components: { Splide, SplideSlide },
    data() {
        return {
            activePage: "javascript",
            skills: [
                {
                    skillName: 'Javascript',
                    skillPicture: require('@/assets/images/skills/javascript.png'),
                    skillCode: 'document.getElementById("skills")',
                },
                {
                    skillName: 'PHP',
                    skillPicture: require('@/assets/images/skills/php.png'),
                    skillCode: "foreach($skills as $skill) { $skill->name };",
                },
                {
                    skillName: 'Laravel',
                    skillPicture: require('@/assets/images/skills/laravel.png'),
                    skillCode: 'php artisan db:seed SkillSeeder',
                },
                {
                    skillName: 'Symfony',
                    skillPicture: require('@/assets/images/skills/symfony.png'),
                    skillCode: 'php bin/console doctrine:fixtures:load',
                },
                {
                    skillName: 'VueJS',
                    skillPicture: require('@/assets/images/skills/vue-js.png'),
                    skillCode: "{{ data() { return { skillCode: skills.code }} }}",
                },
                {
                    skillName: 'Wordpress',
                    skillPicture: require('@/assets/images/skills/wordpress.png'),
                    skillCode: "while ( have_posts() ) { the_post(); }",
                }
            ],
            otherSkills: [
                {
                    skillName: 'Python',
                    skillPicture: require('@/assets/images/skills/python.png'),
                },
                {
                    skillName: 'Django',
                    skillPicture: require('@/assets/images/skills/django.png'),
                },
                {
                    skillName: 'React',
                    skillPicture: require('@/assets/images/skills/react.png'),
                },
                {
                    skillName: 'NodeJS',
                    skillPicture: require('@/assets/images/skills/node-js.png'),
                },
                {
                    skillName: 'Swift',
                    skillPicture: require('@/assets/images/skills/swift.png'),
                },
            ]
        };
    },
}
</script>

<style lang="scss">
    .typewriter h3 {
            max-width: 60vw;
            overflow: hidden; /* Ensures the content is not revealed until the animation */
            border-right: .15em solid orange; /* The typwriter cursor */
            white-space: nowrap; /* Keeps the content on a single line */
            margin: 0 auto; /* Gives that scrolling effect as the typing happens */
            letter-spacing: .15em; /* Adjust as needed */
            animation: 
                typing 3.5s steps(40, end),
                blink-caret .75s step-end infinite;
    }

    /* The typing effect */
    @keyframes typing {
    from { width: 0 }
    to { width: 100% }
    }

    /* The typewriter cursor effect */
    @keyframes blink-caret {
    from, to { border-color: transparent }
    50% { border-color: orange; }
    }

    .splide__pagination {
        bottom: 5em;
    }

    .skill {
        padding: 50px;
        color: #ffffff;
        .skill-title {
            text-align: center;
        }
        .skill-content {
            padding: 50px;
        }
    }
    h2 {
        text-decoration: underline;
        text-underline-offset: 20px;
    }
    .tab {
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        margin: 30px auto;
        img {
            height: 150px;
        }
    }
    .card {
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        border-radius: 20px;
        .nav-tabs {
            list-style: none;
            display: flex;
            
            
        }
        &:last-child {
            h3 {
                text-decoration: underline;
                text-underline-offset: 20px;
                
            }
            color: #fff;
            padding: 0;
            margin: 20px 0 100px 0;
            img {
                height: 100px;
            }
        }

        .otherSkills-content {
            padding-top: 50px;
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            align-items: center;
            gap: 50px;
        }
    }
</style>