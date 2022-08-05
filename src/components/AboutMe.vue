<template>
    <div class='aboutMe'>
        <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css">
        <p class='title'>{{toUppercase(firstName)}} <span style='color: #71c6dd'>{{toUppercase(lastName)}}</span></p>
        <div class='personalInfo'>
            <span style='color: #71c6dd'>{{toUppercase(address)}}</span>
            <span style='color: #8b8b8b'> ~ </span>
            <span>{{toUppercase(state)}}</span>
            <span style='color: #8b8b8b'> ~ </span>
            <span style='color: #71c6dd'>{{toUppercase(country)}}</span>
            <span style='color: #8b8b8b'> ~ </span>
            <a href='`${whatsapp}`' style='color: white; text-decoration: none'>{{phoneNumber}}</a>
            <span style='color: #8b8b8b'> ~ </span>
            <a href='`${mail}`' style='color: #71c6dd; text-decoration: none'>{{toUppercase(email)}}</a>
        </div>
        <p class='about'>{{about}}</p>
        <div class='externalLinks'>
            <a :href='`${github}`' target="_blank"><md-icon class='fa fa-github link'></md-icon></a>
            <a :href='`${linkedin}`' target="_blank"><md-icon class='fa fa-linkedin link' style='color:#71c6dd'></md-icon></a>
            <a :href='`${mail}`' target="_blank"><md-icon class='fa fa-envelope link'></md-icon></a>
            <a :href='`${whatsapp}`' target="_blank"><md-icon class='fa fa-whatsapp link' style='color:#71c6dd'></md-icon></a>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'AboutMe',
        data() {
            return {
                firstName: 'anuj',
                lastName: 'chhabra',
                address: '3/119 geeta colony',
                state: 'delhi 110031',
                country: 'india',
                phoneNumber: '+91 7217746275',
                email: 'anujchhabra.work@gmail.com',
                about: 'Experienced software engineer with a passion for developing innovative programs that expedite the efficiency and effectiveness of organisational success. Well-versed in technology and writing code to create systems that are reliable and user-friendly. \n Confident communicator, strategic thinker, and innovative creator to develop software that is customised to meet a company’s organisational needs, highlight their core competencies, and further their success.',
                github:'https://github.com/chhabranuj',
                linkedin: 'https://www.linkedin.com/in/anuj-chhabra-b0b2a422a',
                mail: 'mailto:anujchhabra.work@gmail.com',
                whatsapp: 'https://wa.me/+917217746275',
                toUppercase(value) {
                    return value.toUpperCase();
                },
            }
        },
    }
</script>

<style scoped>
    @import url('https://fonts.googleapis.com/css2?family=Poppins:wght@600&display=swap');
    @import url('https://fonts.googleapis.com/css2?family=Open+Sans:wght@300&display=swap');
    a:hover {
        text-decoration: underline !important;
    }  
    .aboutMe {
        display: flex;
        justify-content: center;
        align-items: flex-start;
        flex-direction: column;
        min-height: 100vh;
        margin: 0 5%;
        color: white;
    }
    .title {
        font-family: 'Poppins', sans-serif;
        font-size: 80px;
        margin: 0;
    }
    .personalInfo {
        font-family: 'Poppins', sans-serif;
        margin: 0;
        font-size: medium;
    }
    .about {
        font-family: 'Open Sans', sans-serif;
        white-space: pre-line;
        font-size: medium;
        letter-spacing: 1px;
        line-height: 1.5;
        margin: 50px 0;
    }
    .externalLinks {
        display: flex;
    }
    .link {
        margin: 0 20px;
        font-size: 40px;
        cursor: pointer;
        color: white;
    }

    @media screen and (max-width: 900px) {
        .aboutMe {
            padding: 25% 0;
            min-height: auto;
        }
        .title {
            font-size: 60px;
        }
        .personalInfo {
            font-size: 15px;
        }
        .about {
            margin: 30px 0;
        }
     }
</style>