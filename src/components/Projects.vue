<template>
    <div>
        <h2>Projects</h2>
        <div class="projects">
            <div class="project" v-for="project in projects" :key="project">
                <div class="project-image">
                    <img :src="project.image" alt="">
                </div>
                <div class="project-info">
                    <h3>{{ project.title }}</h3>
                    <p>{{ project.year }}</p>
                    <div class="project-languages">
                        <img :src="language" v-for="language in project.languages" :key="language">
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'Projects',
        data() {
            return {
                projects: [
                    {
                        title: 'Forum Associatif Numérique',
                        image: require('@/assets/images/projects/forum-associatif.png'),
                        year: '2021',
                        languages: [
                            require('@/assets/images/skills/symfony.png'),
                        ]
                    },
                    {
                        title: 'Compétences Alternance',
                        image: require('@/assets/images/projects/competences.png'),
                        year: '2021',
                        languages: [
                            require('@/assets/images/skills/laravel.png')
                        ]
                    },
                    {
                        title: 'API d\'associations',
                        image: require('@/assets/images/projects/api.png'),
                        year: '2021',
                        languages: [
                            require('@/assets/images/skills/php.png'),
                            require('@/assets/images/skills/php.png')
                        ]
                    }
                ]
            }
        },
    }
</script>

<style lang="scss">
    .projects {
        min-height: 70vh;
        width: 80%;
        margin: 0 auto;
        display: flex;
        flex-wrap: wrap;
        justify-content: center;
        align-items: center;
        .project {
            background: rgba(0, 0, 0, 0.8);
            display: flex;
            width: 40%;
            margin: 20px;
            box-shadow: 0px 0px 5px #ccc;
            
            .project-image {
                width: 100%;

                img {
                    height: 100%;
                    object-fit: cover;
                    width: 100%;
                }
            }

            .project-info {
                color: #fff;
                width: 70%;
                display: flex;
                flex-direction: column;
                justify-content: center;
                align-items: center;

                p {
                    color: rgb(87, 87, 87);
                }

                .project-languages {
                    display: flex;
                    flex-wrap: wrap;

                    img {
                        width: 50px;
                        margin: 10px;
                    }
                }
            }
        }
    }
    
        @media screen and (max-width: 1200px) {
            .projects {
                padding-top: 100px;

                .project {
                    width: 100%;
                    margin: 10px;
                }
            }
            
        }
        @media screen and (max-width: 800px) {
            .projects {
                padding-top: 100px;

                .project {
                    display: block;
                    width: 100%;
                    .project-info {
                        height: 100%;
                        width: 100%;
                    }

                    .project-info {
                        padding-top: 20px;
                    }
                }
            }
            
        }
</style>