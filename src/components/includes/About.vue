<template>
    <div id="about">
        <h2>About Me</h2>
        <div class="content">
            <div class="picture">
                <img :src="require('@/assets/images/crane.jpg')" alt="selfie" class="crane" heigth="100">
            </div>
            <div class="right-about">
                <div class="about-text">
                    <p>
                        Actuellement alternant en 3ème année de développement web à l'IIM Digital School Paris à Nanterre, je suis passionné par la création de sites internet et applications. D'abord attiré par le développement back-end, je me suis principalement formé sur des technologies basées sur le langage PHP. Après certaines formations professionnelles, personnelles et scolaires, j'ai également décidé de me spécialiser dans le développement front-end, ce qui fait de moi un développeur full stack.
                        
                    </p>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    scrollToTop: true,
    name: "Index",
}
</script>

<style lang="scss">
    #about {
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
            text-align: right;
            width: 100%;
            color: black;
            display: flex;
            flex-wrap: wrap;
            justify-content: space-evenly;
            align-items: center;
            padding-bottom: 80px;

            .about-text {
                display: flex;
                flex-wrap: wrap;
                justify-content: center;
                width: 40vw;

                p {
                    line-height: 30px;
                }
            }
        }
    }

    @media screen and (max-width: 1300px) {
        #about {
            .content {
                .about-text {
                    padding: 50px 5px 5px 5px;
                    width: 70vw;
                    text-align: center;
                }
            }
            
        }
    }
</style>