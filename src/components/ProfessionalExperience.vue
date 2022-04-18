<template>
    <div class=professionalExperience>
        <p class='title'><span style='color: #71c6dd'>PROFESSIONAL</span> EXPERIENCE</p>
        <div class='companyAndJoiningDate'>
            <p class='companyName'>{{toUppercase(companyName)}}, <span style='color: #71c6dd'>{{toUppercase(place)}}</span></p>
            <p class='joiningDate'>{{joiningDate}} - <span style='color: #71c6dd'>Present</span></p>
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
                companyName: 'United Health Group',
                place: 'Gurgaon',
                joiningDate: '30 September 2019',
                designation: 'Software Engineer',
                work: ['Played a Full Stack Engineer role in all the projects Ive worked upon.',
                        'Developed and designed three critical software for Behavioral Health.',
                        'Helped team in designing and understanding the technical requirements of the projects, from the perspective of an architect.',
                        'Worked on all the latest technologies in the market, including React, Azure Cloud, Camunda Engine etc.',
                        'Practiced Micro-Products and Micro-Services.',
                        'Agile Practitioner.',
                        'Been a part of twenties of successful releases.',
                        'Actively taken part in critical situations like war-rooms and priority incidents.',
                        'Saved company a fortune and resolved a critical security threat, by submitting a bright idea every year.'
                ],
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