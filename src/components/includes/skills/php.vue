<template>
    <div class="skill">
        <h3 class="skill-title">{{skillName}}</h3>
        <div class="skill-content">
            <div class="left">
                <div class="typewriter">
                    <h3>{{skillCode}}</h3>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'PHP',
        data() {
            return {
                skillName: 'PHP',
                skillPicture: '/assets/images/skills.jpg',
                skillText: "PHP hfbzejkfvzgerbkjfghazergfkjlerbhggjkzhgbjrhgfrbhgjqhfgzn zghnerjghej",
                skillCode: "foreach($skills as $skill) { $skill->name };"
            }
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
</style>