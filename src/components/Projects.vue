<template>
    <div class='projects' v-bind:class='getMobileHeightClass(data.title)'>
        <p v-bind:class='getTitleClass(data.title)'>{{toUppercase(data.title)}}</p>
        <div class='awards'  v-for='item in data.projects' :key='item.description'>
            <div class='titleAndYear'>
                <p v-bind:class='getProjectNameClass(data.title)'>{{toUppercase(item.title)}}</p>
                <p class='year'>{{item.year}}</p>
            </div>
            <a :href='`${item.url}`' target="_blank" v-bind:class='getUrlClass(data.title)'>{{item.url}}</a>
            <p class='description'>{{item.description}}</p>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'Projects',
        props: [
            'content'
        ],
        data() {
            return {
                data: {},
            }
        },
        beforeMount(){
            this.data = JSON.parse(JSON.stringify(this.content));
        },
        methods: {
            toUppercase(value) {
                return value.toUpperCase();
            },
            getTitleClass(value) {
                if(value == 'projects') {
                    return 'title whiteTitle'
                }
                else {
                    return 'title blueTitle'
                }
            },
            getUrlClass(value) {
                if(value == 'projects') {
                    return 'url whiteTitle'
                }
                else {
                    return 'url blueTitle'
                }
            },
            getProjectNameClass(value) {
                if(value == 'projects') {
                    return 'projectName blueTitle'
                }
                else {
                    return 'projectName whiteTitle'
                }
            },
            getMobileHeightClass(value) {
                if(value == 'projects') {
                    return 'projects'
                }
                else {
                    return 'projects mobileHeight'
                }
            }

        }
    }
</script>

<style scoped>
    @import url('https://fonts.googleapis.com/css2?family=Poppins:wght@600&display=swap');
    @import url('https://fonts.googleapis.com/css2?family=Open+Sans:wght@300&display=swap');
    @import url('https://fonts.googleapis.com/css2?family=Akshar&display=swap');
    .projects {
        display: flex;
        justify-content: center;
        align-items: flex-start;
        flex-direction: column;
        margin: 5%;
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
    .projectName {
        font-family: 'Poppins', sans-serif;
        font-size: 25px;
        margin-bottom: 5px;
    }
    .year {
        font-family: 'Open Sans', sans-serif;
    }
    .url {
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
        .projects {
            min-height: auto;
            padding: 25% 0;
        }
        .mobileHeight {
            padding-bottom: 15%;
        }
        .title {
            font-size: 35px;
            margin: 0 0 15px 0;
        }
        .titleAndYear {
            align-items: flex-start;
            flex-direction: column;
        }
        .projectName {
            font-size: 20px;
        }
        .description {
            font-family: 'Open Sans', sans-serif;
            line-height: 1.5;
            letter-spacing: 1px;
            font-weight: bold;
            font-size: 15px;
        }
        .url {
            font-size: 18px;
        }
        .urlHackathonMobile {
            color: white;
        }
        .description {
            width: 100%;
        }
    }
</style>