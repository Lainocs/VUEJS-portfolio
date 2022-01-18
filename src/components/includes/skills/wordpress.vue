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
        name: 'Wordpress',
        data() {
            return {
                skillName: 'Wordpress',
                skillPicture: '/assets/images/skills.jpg',
                skillText: "WORDPRESS hfbzejkfvzgerbkjfghazergfkjlerbhggjkzhgbjrhgfrbhgjqhfgzn zghnerjghej",
                skillCode: "while ( have_posts() ) { the_post(); }"
            }
        },
    }
</script>