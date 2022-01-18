<template>
    <div id="cards">
    <h2>What are you lookin' for ?</h2>
        <div class="container">
            <div class="link" @click="setActivePage(1)">
                <div class="flip-card">
                    <div class="flip-card-inner">
                        <div class="flip-card-front">
                            <img :src="require('@/assets/images/profile_picture.png')" alt="Avatar" style="width:300px;height:400px;">
                            <p class="description">About-me</p>
                        </div>
                        <div class="flip-card-back">
                            <h3>About Me</h3> 
                            <p>Discover me</p> 
                        </div>
                    </div>
                </div>
            </div>
            <div class="link" @click="setActivePage(2)">
                <div class="flip-card">
                    <div class="flip-card-inner">
                        <div class="flip-card-front">
                            <img :src="require('@/assets/images/skills.jpg')" alt="Avatar" style="width:300px;height:400px;">
                            <p class="description">Projects</p>
                        </div>
                        <div class="flip-card-back">
                            <h3>Projects</h3> 
                            <p>Look what I've done</p>
                        </div>
                    </div>
                </div>
            </div>
            <div class="link" @click="setActivePage(3)">
                <div class="flip-card">
                    <div class="flip-card-inner">
                        <div class="flip-card-front">
                            <img :src="require('@/assets/images/contact.jpg')" alt="Avatar" style="width:300px;height:400px;">
                            <p class="description">Contact</p>
                        </div>
                        <div class="flip-card-back">
                            <h3>Contact</h3> 
                            <p>Leave a message after the ***bip***</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'Cards',
        methods: {
            setActivePage(id) {
                this.$emit('active-page', id);
            }
        },
    }
</script>

<style lang="scss">
    #cards {
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: space-around;
        min-height: 100vh;
        margin: 0 auto;
        width: 90vw;

        .container {
            display: flex;
            flex-wrap: wrap;
            align-items: center;
            justify-content: center;
            padding: 10px;

            .description {
                position: absolute;
                bottom: 20px;
                right: 10%;
                color: white;
                background-color: rgba(0, 0, 0, 0.5);
                padding: 10px 20px;
            }
        }

        .flip-card {
            margin: 20px;
            background-color: transparent;
            width: 300px;
            height: 400px;
            perspective: 1000px;
        }

        .flip-card-inner {
            position: relative;
            width: 100%;
            height: 100%;
            text-align: center;
            transition: transform 0.6s;
            transform-style: preserve-3d;
            box-shadow: 0 4px 8px 0 rgba(0,0,0,0.2);
        }

        .flip-card:hover .flip-card-inner {
            transform: rotateY(180deg);
        }

        .flip-card-front, .flip-card-back {
            position: absolute;
            width: 100%;
            height: 100%;
            -webkit-backface-visibility: hidden;
            backface-visibility: hidden;
        }

        .flip-card-front {
            background-color: #bbb;
            color: black;
                img {
                    object-fit: cover;
                }
        }

        .flip-card-back {
            display: flex;
            flex-direction: column;
            justify-content: center;
            background-color: #161616;
            color: white;
            transform: rotateY(180deg);
        }
    }
    
</style>