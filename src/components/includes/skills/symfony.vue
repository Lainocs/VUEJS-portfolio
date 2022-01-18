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
        name: 'Symfony',
        data() {
            return {
                skillName: 'Symfony',
                skillPicture: '/assets/images/skills.jpg',
                skillText: "SYMFONY hfbzejkfvzgerbkjfghazergfkjlerbhggjkzhgbjrhgfrbhgjqhfgzn zghnerjghej",
                skillCode: "php bin/console server:start -d"
            }
        },
    }
</script>