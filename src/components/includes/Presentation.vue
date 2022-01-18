<template>
    <div id="presentation">
        <img :src="require('@/assets/images/profile_picture.jpg')" alt="profile_picture">
        <h1>Nicolas de Garrigues</h1>
        <h2>Full Stack Web Developer</h2>
    </div>
</template>

<script>
    export default {
        name: 'Presentation',
    }
</script>
<style lang="scss">
#presentation {
    min-height: 100vh;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    color: #fff;
    padding-bottom: 100px;
    img {
    box-shadow: 4px 8px 8px black;
    border-radius: 200px;
    width: 300px;
    }
    
    h1 {
    line-height: 50px;
    }
}
h2 {
    line-height: 70px;
    text-align: center;
    color: #fff;
    padding: 50px 50px 0 50px;
}
</style>