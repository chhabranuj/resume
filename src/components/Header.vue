<template>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css">
    <div class='header'>
        <img src='./../assets/anuj.jpeg' class='image'/>
        <p class='contents' v-for='item in content' :key="item">{{item}}</p>
    </div>
    <div class='mediaHeader'>
        <div class='mediaTitleAndMenu'>
            <p class='title'><span style='color: #71c6dd'>{{firstName}}</span> {{lastName}} </p>
            <md-icon class='fa fa-bars menu' @click='menuIsOpen = !menuIsOpen'></md-icon>
        </div>
        <div class='mediaContents' v-if='menuIsOpen'>
            <p class='mediaContent contents' v-for='item in content' :key="item">{{item}}</p>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'Header',
        data() {
            return {
                firstName: 'Anuj',
                lastName: 'Chhabra',
                content: ['ABOUT ME', 'PROFESSIONAL \n EXPERIENCE', 'EDUCATION', 'SKILLS', 'ACHIEVEMENTS', 'HACKATHON'],
                menuIsOpen: false,
            }
        },
    }
</script>

<style scoped>
    @import url('https://fonts.googleapis.com/css2?family=Fira+Sans:wght@600&display=swap');
    .mediaHeader {
        display: none;
    }
    .header {
        display: flex;
        justify-content: center;
        align-items: center;
        flex-direction: column;
        width: 280px;
        height: 100vh;
        background-color: #51546e;
    }
    .image {
        width: 50%;
        height: 18%;
        border-radius: 50%;
        border: 10px solid rgba(255, 255, 255, .1);
        margin-bottom: 25px;
    }
    .contents {
        color: rgba(255, 255, 255, 0.5);
        font-family: 'Fira Sans', sans-serif;
        text-align: center;
        letter-spacing: 1.5px;
        cursor: pointer;
        white-space: pre-line;
    }
    .contents:hover {
        color: white;
    }

    @media screen and (max-width:900px) {
        .header {
            display: none;
        }
        .mediaHeader {
            display: flex;
            justify-content: center;
            align-items: flex-start;
            flex-direction: column;
            padding: 0 2%;
            color: white;
            background-color: #51546e;
            top: 0;
            z-index: 1000;
            position: absolute;
            width: 96%;
        }
        .mediaTitleAndMenu {
            display: flex;
            justify-content: space-between;
            align-items: center;
            width: 100%;
        }
        .title {
            font-family: 'Poppins', sans-serif;
            font-size: 25px;
            margin: 15px 0;
        }
        .menu {
            padding: 5px 10px;
            border: 1.5px solid rgba(255, 255, 255, 0.1);
            border-radius: 5px;
            font-size: 20px;
            cursor: pointer;
            
        }
        .mediaContents {
            display: flex;
            align-items: flex-start;
            flex-direction: column;
        }
        .mediaContent {
            text-align: start;
            margin: 10px 0;
        }
    }
</style>