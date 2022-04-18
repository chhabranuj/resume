<template>
    <div class='achievements'>
        <p class='title'>ACHIEVEMENTS</p>
    </div>
</template>

<script>
    export default {
        name: 'Achievements',
        data() {
            return {

            }
        },
    }
</script>

<style scoped>
    @import url('https://fonts.googleapis.com/css2?family=Poppins:wght@600&display=swap');
    @import url('https://fonts.googleapis.com/css2?family=Open+Sans:wght@300&display=swap');
    @import url('https://fonts.googleapis.com/css2?family=Akshar&display=swap');
    .achievements {
        display: flex;
        justify-content: center;
        align-items: flex-start;
        flex-direction: column;
        margin: 0 5%;
        min-height: 100vh;
        color: white;
    }
    .title {
        font-family: 'Poppins', sans-serif;
        font-size: 50px;
        margin: 0 0 20px 0;
    }
</style>