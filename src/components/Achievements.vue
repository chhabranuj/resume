<template>
    <div class='achievements'>
        <p v-bind:class='getTitleClass(data.title)'>{{toUppercase(data.title)}}</p>
        <div class='awards'  v-for='item in data.achievements' :key='item.description'>
            <div class='titleAndYear'>
                <p v-bind:class='getAwardTitleClass(data.title)'>{{toUppercase(item.award)}}</p>
                <p class='year'>{{item.year}}</p>
            </div>
            <p v-bind:class='getFromClass(data.title)'>{{toUppercase(item.from)}}</p>
            <p class='description'>{{item.description}}</p>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'Achievements',
        props: [
            'content'
        ],
        data() {
            return {
                data: {},
            }
        },
        beforeMount(){
            this.data = JSON.parse(JSON.stringify(this.content))
        },
        methods: {
            toUppercase(value) {
                return value.toUpperCase();
            },
            getTitleClass(value) {
                if(value == 'achievements') {
                    return 'title whiteTitle'
                }
                else {
                    return 'title blueTitle'
                }
            },
            getFromClass(value) {
                if(value == 'achievements') {
                    return 'from whiteTitle'
                }
                else {
                    return 'from blueTitle'
                }
            },
            getAwardTitleClass(value) {
                if(value == 'achievements') {
                    return 'awardTitle blueTitle'
                }
                else {
                    return 'awardTitle whiteTitle'
                }
            }
        }
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
    .blueTitle {
        color: #71c6dd !important;
    }
    .whiteTitle {
        color: white !important;
    }
    .awards {
        margin: 8px 0;
        width: 100%;
    }
    .titleAndYear {
        display: flex;
        justify-content: space-between;
        align-items: center;
    }
    .awardTitle {
        font-family: 'Poppins', sans-serif;
        font-size: 25px;
        margin-bottom: 5px;
    }
    .year {
        font-family: 'Open Sans', sans-serif;
    }
    .from {
        font-family: 'Open Sans', sans-serif;
        font-size: 20px;
        font-weight: bold;
        margin-top: 5px;
        color: rgba(255, 255, 255, 0.6);
    }
    .description {
        font-family: 'Open Sans', sans-serif;
        font-size: 18px;
        width: 75%;
    }
    .divider {
        border: 0;
        border-top: 1px solid rgba(255, 255, 255, 0.1);
        width: 100%;
    }
    @media screen and (max-width: 900px) {
        .achievements {
            min-height: auto;
            padding: 25% 0;
        }
        .title {
            font-size: 35px;
            margin: 0 0 15px 0;
        }
        .titleAndYear {
            align-items: flex-start;
            flex-direction: column;
        }
        .awardTitle {
            font-size: 20px;
        }
        .description {
            font-family: 'Open Sans', sans-serif;
            line-height: 1.5;
            letter-spacing: 1px;
            font-weight: bold;
            font-size: 15px;
        }
        .from {
            font-size: 18px;
        }
        .fromHackathonMobile {
            color: white;
        }
        .description {
            width: 100%;
        }
    }
</style>