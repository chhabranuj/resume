<template>
    <div class=professionalExperience>
        <p class='title'><span style='color: #71c6dd'>PROFESSIONAL</span> EXPERIENCE</p>
        <div class='companyAndJoiningDate'>
            <p class='companyName'>{{toUppercase(companyName)}}, <span style='color: #71c6dd'>{{toUppercase(place)}}</span></p>
            <p class='joiningDate'>{{joiningDate}} - <span style='color: #71c6dd'>{{endingDate}}</span></p>
        </div>
        <p class='designation'>{{toUppercase(designation)}}</p>
        <ul class='work'>
            <li class='workContent' v-for='item in work' :key='item'><span style='color: white'>{{item}}</span></li>
        </ul>
    </div>
</template>

<script>
    export default {
        name: 'ProfessionalExperience',
        data() {
            return {
                companyName: 'Alecado Systems',
                place: 'Remote',
                joiningDate: '1 May 2022',
                endingDate: '31 May 2022',
                designation: 'Web Developer Intern',
                work: [
                    'Worked with software development team members to design and develop robust solutions to meet the product requirements for functionality, scalability and performance.',
                    'Helped team in designing and understanding the technical requirements of the projects, from the perspective of an architect.',
                    'Worked on all the latest technologies in the market, including Reactjs, Nodejs, Html, Css.',
                    'Actively taken part in all the situations wherever needed.',
                    'Saved company a time and money by submitting a bright idea every week.',
                ],
            }
        },
        methods: {
            toUppercase(value) {
                return value.toUpperCase();
            },
        }
    }
</script>

<style scoped>
    @import url('https://fonts.googleapis.com/css2?family=Poppins:wght@600&display=swap');
    @import url('https://fonts.googleapis.com/css2?family=Open+Sans:wght@300&display=swap');
    @import url('https://fonts.googleapis.com/css2?family=Akshar&display=swap');
    .professionalExperience {
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
    .companyAndJoiningDate {
        display: flex;
        justify-content: space-between;
        align-items: center;
        width: 100%;
    }
    .companyName {
        font-family: 'Poppins', sans-serif;
        font-size: 28px;
        letter-spacing: 1px;
        margin: 0;
    }
    .joiningDate {
        font-family: 'Open Sans', sans-serif;
    }
    .designation {
        margin: 0;
        font-family: 'Akshar', sans-serif;
        letter-spacing: 2px;
        font-size: 22px;
        color: rgba(255, 255, 255, 0.6);
    }
    .work {
        margin-top: 10px;
    }
    .workContent {
        font-family: 'Open Sans', sans-serif;
        line-height: 2;
        font-weight: bold;
        color: #71c6dd;
    }
    @media screen and (max-width: 900px) {
        .professionalExperience { 
            min-height: auto;
            padding: 25% 0;
        }
        .title {
            font-size: 35px;
            margin: 0 0 25px 0;
        }
        .companyAndJoiningDate {
            align-items: flex-start;
            flex-direction: column;
        }
        .companyName {
            font-size: 22px;
        }
    }
 </style>