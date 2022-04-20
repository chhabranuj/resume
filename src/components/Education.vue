<template>
    <div class='education'>
        <p class='title'>EDUCATION</p>
        <div class='educationDetails'>
            <p class='college'><span style='color: #71c6dd'>{{toUppercase(collegeName)}}</span>, {{toUppercase(universityName)}}, <span style='color:#71c6dd'>{{toUppercase(state)}}</span></p>
            <p class='years'><span style='color: #71c6dd'>{{startingYear}}</span> - {{finalYear}}</p>
        </div>
        <p class='degree'>{{toUppercase(degree)}}</p>
        <p class='about'>{{about}}</p>
    </div>
</template>

<script>
    export default {
        name: 'Education',
        data() {
            return {
                collegeName: 'delhi technical campus',
                universityName: 'ggsipu',
                state: 'delhi',
                startingYear: '2015',
                finalYear: '2019',
                degree: 'bachelor of technology in computer science',
                about: 'BTech CSE is a 4 year UG course that studies practical and theoretical knowledge of computer hardware and software. This course lays emphasis on the basics of computer programming and networking while also comprising a plethora of topics.',
                toUppercase(value) {
                    return value.toUpperCase();
                }
            }
        },
    }
</script>

<style scoped>
    @import url('https://fonts.googleapis.com/css2?family=Poppins:wght@600&display=swap');
    @import url('https://fonts.googleapis.com/css2?family=Open+Sans:wght@300&display=swap');
    @import url('https://fonts.googleapis.com/css2?family=Akshar&display=swap');
    .education {
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
        font-size: 45px;
        margin: 0 0 20px 0;
    }
    .educationDetails {
        display: flex;
        justify-content: space-between;
        align-items: center;
        width: 100%;
    }
    .college {
        font-family: 'Poppins', sans-serif;
        font-size: 28px;
        margin: 0;
    }
    .years {
        font-family: 'Open Sans', sans-serif;
    }
    .degree {
        margin: 0 0 20px 0;
        font-family: 'Akshar', sans-serif;
        letter-spacing: 1px;
        font-size: 22px;
        color: rgba(255, 255, 255, 0.6);
    }
    .about {
        font-family: 'Open Sans', sans-serif;
        line-height: 1.5;
        letter-spacing: 1px;
        font-weight: bold;
        font-size: 15px;
        width: 75%;
    }
    @media screen and (max-width: 900px) {
        .education {
            padding: 25% 0;
            min-height: auto;
        }
        .title {
            font-size: 35px;
            margin: 0 0 25px 0;
        }
        .educationDetails {
            align-items: flex-start;
            flex-direction: column;
        }
        .college {
            font-size: 22px;
        }
    }
</style>