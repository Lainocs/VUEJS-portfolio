<template>
    <div id="projects">
        <h2>Projects</h2>
        <div class="content">
            <div class="right-about">
                <div class="about-text">
                    <p>
                        Actuellement Etudiant en 3ème année de Développement Web à l'IIM Digital School Paris, je me suis
                        <i>développé</i> une passion pour la création de sites internet et d'applications. Cette passion se
                        reflète dans les différents projets sur lesquels j'ai pu travailler jusqu'à présent, qu'ils soient
                        scolaires, personnels ou professionnels
                    </p>
                </div>
            </div>
            <div class="picture">
                <img :src="require('@/assets/images/projects/api.png')" alt="api">
                <img :src="require('@/assets/images/projects/competences.png')" alt="competences">
                <img :src="require('@/assets/images/projects/forum-associatif.png')" alt="forum associatif">
            </div>
        </div>
        <!-- NuxtLink -->
        <span class="see-more" @click="changeActive">Voir mes projets</span>
    </div>

    <!-- <div id="cards">
        <Cards />
    </div>
     -->
</template>

<script>
    export default {
        name: 'Projects',
        methods: {
            changeActive() {
                this.$emit('active-page', 2);
            }
        },
    }
</script>

<style lang="scss">

    #projects {
        margin: 0 auto;
        width: 80vw;
        border-radius: 10px;
        background-color: rgba(236, 236, 236, 0.9);
        min-height: 50vh;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: space-around;
        align-items: center;

        h2 {
            color: black;
            text-decoration: underline;
            text-underline-offset: 20px;
            padding: 50px;
        }

        .content {
            width: 100%;
            color: black;
            display: flex;
            flex-wrap: wrap;
            justify-content: space-evenly;
            align-items: center;
            padding-bottom: 80px;

            .about-text {
                text-align: left;
                padding: 20px;
                display: flex;
                flex-wrap: wrap;
                justify-content: center;
                width: 40vw;

                p {
                    line-height: 30px;
                }
            }

            .picture {
                height: 300px;
                width: 500px;
                position: relative;
                img {
                    width: 300px;
                    height: auto;
                    object-fit: cover;
                    &:nth-child(1) {
                    position: absolute;
                    right: 0;
                    top: 0;
                    }
                    &:nth-child(2) {
                    position: absolute;
                    right: 50px;
                    top: 50px;
                    }
                    &:nth-child(3) {
                    position: absolute;
                    right: 100px;
                    top: 100px;
                    }
                }
            }
        }
        .see-more {
            text-align: center;
            text-decoration: none;
            background-color: rgba(22, 22, 22, 0.9);
            color: white;
            border: none;
            border-radius: 10px;
            padding: 10px;
            margin: 20px 0 80px 0;
            width: 200px;
            font-size: 20px;
            cursor: pointer;

            &:hover {
                background-color: rgba(22, 22, 22, 0.8);
            }

        }
    }
    @media screen and (max-width: 1300px) {  
        #projects {
            .content {
                padding-bottom: 0;
                .picture {
                    padding-bottom: 50px;
                    order: -1;
                    height: auto;
                    width: 100%;
                    position: initial;
                    img {
                        display: none;
                    }
                    img:nth-child(3) {
                        display: block;
                        position: initial;
                        margin: 0 auto;
                    }
                }
                .about-text {
                    padding: 5px;
                    width: 70vw;
                    text-align: center;
                }
            }
        }
    }
</style>