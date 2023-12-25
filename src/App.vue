<template>
  <div id="app">
    <Header @clicked="getItemName" />
    <div class="contents">
      <AboutMe class="ABOUT ME" :about="content.about" />
      <hr class="divider" />
      <ProfessionalExperience class="PROFESSIONAL EXPERIENCE" :professionalExperience="content.professionalExperience" />
      <hr class="divider" />
      <Education class="EDUCATION" :education="content.education" />
      <hr class="divider" />
      <Skills class="SKILLS" :skills="content.skills" />
      <hr class="divider" />
      <Projects class="PROJECTS" :projects="content.projects" />
      <hr class="divider" />
      <Certificates class="CERTIFICATES" :certificates="content.certificates" />
      <hr class="divider" />
      <Volunteerings class="VOLUTEERINGS" :volunteerings="content.volunteerings" />
    </div>
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Skills from "./components/Skills.vue";
import AboutMe from "./components/AboutMe.vue";
import Projects from "./components/Projects.vue";
import Education from "./components/Education.vue";
import Certificates from "./components/Certificates.vue";
import Volunteerings from "./components/Volunteering.vue";
import ProfessionalExperience from "./components/ProfessionalExperience.vue";

export default {
  name: "App",
  components: {
    Header,
    AboutMe,
    ProfessionalExperience,
    Education,
    Skills,
    Projects,
    Certificates,
    Volunteerings,
  },
  data() {
    return {
      el: "#app",
      content: {
        about: {
          firstName: "anuj",
          lastName: "chhabra",
          address: "3/119 geeta colony",
          state: "delhi 110031",
          country: "india",
          phoneNumber: "+91 7217746275",
          email: "anujchhabra.work@gmail.com",
          about:
            "A final year B.Tech CSE student with a passion for web development, backed by valuable experience in creating innovative and interactive websites. Proficient in front-end technologies and well-versed in using various frameworks and libraries to build responsive and user-friendly interfaces. \n\nDemonstrated ability to work on diverse projects, honing problem-solving and teamwork skills. Through a combination of academic excellence and hands-on experience, I have developed a deep understanding of web development principles and is excited to embark on a fulfilling career in the tech industry, bringing creativity and technical expertise to any team or organization.",
          github: "https://github.com/chhabranuj",
          linkedin: "https://www.linkedin.com/in/chhabranuj",
          mail: "mailto:anujchhabra.work@gmail.com",
          whatsapp: "https://wa.me/+917217746275",
        },
        professionalExperience: [
          {
            companyName: "Orsoot LLP",
            place: "Remote",
            joiningDate: "Sept 2023",
            endingDate: "Oct 2023",
            designation: "Vue.js Developer",
            url: "https://drive.google.com/file/d/1t-9no9P7dl1MOGUmSfRuEpIADKMywrID/view?usp=drivesdk",
            work: [
              "Design, develop, and maintain websites and web applications. Create user-friendly interfaces and ensure a seamless user experience.",
              "Develop the visual elements and user interface of websites. Write clean, efficient HTML, CSS, JavaScript in React and Vue.",
              "Work closely with designers, UX/UI specialists, and other developers to bring designs to life. Collaborate with cross-functional teams to define project requirements and goals.",
              "Identify and troubleshoot technical issues, bugs, and other challenges. Find creative solutions to optimize website performance and user experience.",
            ],
          },
          {
            companyName: "TechnoHacks",
            place: "Remote",
            joiningDate: "June 2023",
            endingDate: "July 2023",
            designation: "Web Developer",
            url: "https://drive.google.com/file/d/1t64JWJBqLjIXiiYvNqoXaXahxDD9ID9f/view?usp=drivesdk",
            work: [
              "Worked on three projects during my internship period.",
              "Created web applications using Html, Css, Javascript in React.",
              "The projects that I have worked on includes a fully working calculator with advance formulas used in applied and computational mathematics.",
              "Also worked on the currency converter, that converts currency with real time data. This application includes more than 100 cuntries and used an api integration that gives real time data."
            ],
          },
          {
            companyName: "Alecado Systems",
            place: "Remote",
            joiningDate: "May 2022",
            endingDate: "June 2022",
            designation: "Web Developer Intern",
            url: "https://drive.google.com/file/d/1t5J_xQWgjS38Aas84SwdXFDHrgHH9aTa/view?usp=drivesdk",
            work: [
              "Worked with software development team members to design and develop robust solutions to meet the product requirements for functionality, scalability and performance.",
              "Helped team in designing and understanding the technical requirements of the projects, from the perspective of an architect.",
              "Worked on all the latest technologies in the market, including Reactjs, Nodejs, Html, Css.",
              "Actively taken part in all the situations wherever needed.",
              "Saved company a time and money by submitting a bright idea every week.",
            ],
          },
        ],
        education: [
          {
            institute: "delhi technical campus",
            universityName: "ggsipu",
            state: "delhi",
            startingYear: "2020",
            finalYear: "2024",
            degree: "bachelor of technology in computer science",
            grade: "(90.3%)",
            description:
              "A Bachelor of Technology (B.Tech) in Computer Science is a popular undergraduate degree program that focuses on the principles and applications of computer science and technology. During the course, students delve into various facets of computing, including programming languages, algorithms, data structures, software engineering, database management, artificial intelligence, and networking.",
          },
          {
            institute: "st. lawrence convent",
            universityName: "cbse",
            state: "delhi",
            startingYear: "2019",
            finalYear: "2020",
            degree: "hsc: non-medical",
            grade: "(83%)",
            description:
              "HSC (Higher Secondary Certificate) in the non-medical stream is an important stage in the Indian education system. It is typically undertaken after the completion of grade 10 (SSC or CBSE) and marks the final two years of pre-university education. In the non-medical stream, students choose subjects such as Physics, Chemistry, Mathematics, English and Computer Science.",
          },
          {
            institute: "st. lawrence convent",
            universityName: "cbse",
            state: "delhi",
            startingYear: "2017",
            finalYear: "2018",
            degree: "ssc: cbse basics",
            grade: "(83.6%)",
            description:
              "SSC (Secondary School Certificate) and CBSE (Central Board of Secondary Education) are fundamental components of the Indian education system. SSC is a public examination conducted at the state level, usually at the end of grade 10, to assess students' knowledge and understanding of the prescribed curriculum. It is an essential milestone for students to progress to higher education or various vocational courses.",
          },
        ],
        skills: {
          technologies: [
            "React JS",
            "Next JS",
            "Angular JS",
            "Node.js",
            "Vue JS",
            "Next JS",
            "GraphQL",
            "MongoDB",
            "AWS(S3)",
            "Pyhton",
            "C++",
            "Java",
          ],
          workflow: [
            "Get the product details from the client.",
            "Develop & Design the Product.",
            "Work arounds for in-change.",
          ],
        },
        projects: [
          {
            title: "exam crafter",
            url: "https://youtu.be/v-Qv4SH9jSo",
            startDate: "Sept 2023",
            endDate: "Dec 2023",
            description: [
              "Exam Crafter is a personalized secure framework for exam preperation using AI.",
              "Exam Crafter is a digital exam preparation website that uses artificial intelligence (AI) to generate personalized questions and practice exams for a variety of subjects and exams.",
              "Our Al-powered question bank is constantly being updated with new and challenging questions, so you can be sure that you're getting the best possible preparation.",
              "With Exam Crafter, you can prepare for your exams in a way that is tailored to your individual needs",
              "Technology Used:- Next.js, Next-Auth, Docker, MongoDB.",
            ],
          },
          {
            title: "onehowl",
            url: "https://github.com/chhabranuj/onehowl",
            startDate: "Nov 2022",
            endDate: "Dec 2022",
            description: [
              "Onehowl is an innovative e-commerce website that I successfully created.",
              "Designed with a user-friendly interface and a sleek, modern aesthetic, the platform offers a more than 100 of products across various categories.",
              "Through Onehowl, customers can easily browse and purchase items, enjoy a seamless checkout process, and receive timely order updates.",
              "Moreover, Onehowl includes dynamic search and filtering options, allowing users to find products tailored to their preferences.",
              "Technology Used:- Next.js, Next-Auth, Docker, Redux, AWS(S3), MongoDB.",
            ],
          },
          {
            title: "hitchdoc",
            url: "https://github.com/chhabranuj/hitchdoc",
            startDate: "July 2022",
            endDate: "Aug 2022",
            description: [
              "Hitchdoc is a user-friendly document saver website that I developed to streamline the process of storing and organizing important documents.",
              "With its intuitive interface, users can effortlessly upload and categorize their documents, ensuring easy access and retrieval whenever needed.",
              "The website employs robust security measures to safeguard sensitive information, providing peace of mind to users. Hitchdoc also includes powerful search functionality, enabling users to quickly locate specific documents within their collection.",
              "As the creator of Hitchdoc, I aimed to simplify document management and create a convenient solution for individuals and businesses alike to store and manage their important files securely and efficiently.",
              "Technology Used:- Next.js, Next-Auth, Docker, MongoDB, AWS(S3).",
            ],
          },
          {
            title: "amazon admin clone",
            url: "https://github.com/chhabranuj/amazon-admin-clone",
            startDate: "May 2022",
            endDate: "June 2022",
            description: [
              "The Amazon Admin Clone is a product entering website that I designed and developed to simplify the process of adding new products to an e-commerce platform.",
              "With a user-friendly interface, this clone offers a seamless way for sellers and administrators to enter product details, including titles, descriptions, prices, and images.",
              "The platform ensures efficient categorization and tagging, making it easier for customers to find products.",
              "With its intuitive design and emphasis on accuracy and efficiency, this clone serves as a valuable tool for e-commerce businesses to expand their product offerings and enhance the overall shopping experience for their customers.",
              "Technology Used:- React.js, Node.js.",
            ],
          },
          {
            title: "amazon clone",
            url: "https://github.com/chhabranuj/amazon-clone",
            startDate: "May 2022",
            endDate: "June 2022",
            description: [
              "The Amazon Clone website that I created is a read-only replica of the popular e-commerce platform, Amazon.",
              "While users can browse and explore a wide range of products and categories that are added by the admin from Amazon-Admin Website.",
              "The website provides a user-friendly interface with advanced search and filtering options, allowing visitors to find products based on their preferences.",
              "Additionally, the clone offers detailed product pages with images, descriptions, and customer reviews to help users make informed decisions. ",
              "Technology Used:- React.js, Node.js.",
            ],
          },
          {
            title: "dunphy",
            url: "https://github.com/chhabranuj/dunphy/",
            startDate: "Mar 2022",
            endDate: "Apr 2022",
            description: [
              "Dunphy is a messaging website that I developed, offering a straightforward and efficient platform for sending messages.",
              "With a minimalist interface, Dunphy enables users to exchange text messages in real-time without the complexity of multimedia features.",
              "The website emphasizes speed and simplicity, providing a seamless communication experience for individuals who prefer text-based interactions. ",
              "Preview:- https://dunphy.netlify.app/",
              "Technology Used:- React.js, Node.js, MongoDB.",
            ],
          },
          {
            title: "pen down on paper",
            url: "https://github.com/chhabranuj/pendownonpaper",
            startDate: "Jan 2022",
            endDate: "Feb 2022",
            description: [
              "Pendownonpaper is a user-friendly website that I developed, dedicated to showcasing a captivating collection of wallpapers for users to explore and download.",
              "With a sleek and intuitive interface, visitors can easily browse through an extensive gallery of high-quality wallpapers, encompassing various themes and styles to suit different preferences.",
              "The website offers a seamless download process, allowing users to effortlessly save their favorite wallpapers for personalizing their desktops, laptops, smartphones, or tablets.",
              "With a focus on providing an enjoyable and aesthetically pleasing experience, Pendownonpaper is the go-to destination for wallpaper enthusiasts to find inspiring and visually stunning backgrounds for their digital devices.",
              "Technology Used:- Angular.js, GraphQl.",
            ],
          },
          {
            title: "property pustak",
            url: "https://github.com/chhabranuj/property-pustak/",
            startDate: "Nov 2021",
            endDate: "Dec 2021",
            description: [
              "Property Pustak is a digital details saver website designed to streamline the process of storing and managing property-related information.",
              "With its user-friendly interface, users can easily input and organize details of properties they own or are interested in, such as addresses, descriptions and important documents.",
              "The website ensures data security and privacy, and filtering system, making it effortless to retrieve specific property details.",
              "Whether for personal or professional use, Property Pustak is a reliable platform to keep all property-related information in one centralized and easily accessible location, simplifying property management and organization.",
              "Technology Used:- Angular.js, GraphQl.",
            ],
          },
        ],
        certificates: [
          {
            title: "Basics of javaScript Programming",
            company: "OpenWeaver",
            url: "https://drive.google.com/file/d/1G3xc_8RAIJC_ye4HCQzXAyvnrqFsNn3G/view?usp=drivesdk",
            date: "June 2023",
            description: [
              "The Basics of JavaScript Programming course provides a solid foundation in JavaScript, one of the most widely used programming languages for web development.",
              "During the course, I learned essential concepts such as variables, data types, operators, functions, and control flow.",
              "I also gained insights into manipulating the Document Object Model (DOM) to create interactive elements and enhance user experience on websites.",
            ],
          },
          {
            title: "TCS iON Career Edge - Young Professional",
            company: "TCS iON",
            url: "https://drive.google.com/file/d/1T56sxm-GV6Ak_YK5cX-3R4Z8inEoz16K/view?usp=drivesdk",
            date: "June 2023",
            description: [
              "The TCS iON Career Edge - Young Professional course is an all-encompassing program that I recently completed, which has significantly enriched my skills and knowledge as a young professional.",
              "Developed by the renowned Tata Consultancy Services (TCS), this course provides a comprehensive curriculum tailored to meet the demands of today's dynamic business and technology landscape.",
              "Throughout the course, I received extensive training in various essential areas. From honing my soft skills, including effective communication and teamwork, to understanding the intricacies of business etiquette and professionalism, the course equipped me with the tools to excel in any professional setting.",
            ],
          },
          {
            title: "Basics of HTML/CSS",
            company: "OpenWeaver",
            url: "https://drive.google.com/file/d/1JG2cDx1apfna1eGtdHn4z7xFQeS6wyLy/view?usp=drivesdk",
            date: "April 2023",
            description: [
              "The HTML/CSS course I completed was an essential stepping stone in my journey as a web developer.",
              "This comprehensive program focused on the fundamentals of HTML (Hypertext Markup Language) and CSS (Cascading Style Sheets) – the backbone of web development.",
              "Throughout the course, I learned how to create and structure web pages using HTML, incorporating various elements like headings, paragraphs, lists, and images. Additionally, the course covered CSS, allowing me to enhance the visual appeal of websites by styling HTML elements, modifying layouts, and implementing responsive design principles",
            ],
          },
        ],
        volunteerings: [
          {
            institute: "gdsc",
            position: "web development head",
            startDate: "Aug 2022",
            endDate: "July 2023",
            description: [
              "As the Web Development Head of the Google Developer Student Club (GDSC) during my third year of college, I led a team of aspiring developers in creating impactful web-based projects and fostering a vibrant tech community on campus.",
              "With a passion for web development and a drive to inspire others, I organized workshops, hackathons, and seminars to impart practical skills and industry insights to fellow students.",
              "Collaborating with my team, I initiated and executed various web development projects, leveraging modern technologies and frameworks to create innovative solutions.",
            ],
          },
          {
            institute: "cesta",
            position: "tech team associate",
            startDate: "Aug 2021",
            endDate: "June 2022",
            description: [
              "As a Cesta - Tech Team Associate during my second year of college , I actively contributed my skills and enthusiasm to the projects and initiatives undertaken by the team.",
              "With a strong foundation in technology and a passion for problem-solving, I collaborated closely with my team members, participating in brainstorming sessions and contributing innovative ideas.",
              "I eagerly engaged in technical workshops and training programs to further enhance my expertise and stay abreast of the latest advancements in the field.",
            ],
          },
          {
            institute: "cesta",
            position: "tech team member",
            startDate: "Jan 2021",
            endDate: "July 2021",
            description: [
              "As a Cesta - Tech Team Member in my first year of college, I was a proactive and dedicated individual, eager to apply my passion for technology and problem-solving skills to real-world projects.",
              "Collaborating with my peers and mentors, I actively contributed to the development of innovative solutions and took part in various technical workshops and hackathons.",
              "Through my work, I demonstrated a strong ability to adapt to new challenges, staying up-to-date with the latest trends in the technology industry.",
            ],
          },
        ],
      },
    };
  },
  methods: {
    getItemName(value) {
      const ele = this.$el.getElementsByClassName(value)[0];
      ele.scrollIntoView({ behavior: "smooth" });
    },
  },
};
</script>

<style scoped>
#app {
  display: flex;
  width: 100%;
}

.contents {
  width: calc(100% - 300px);
  height: 100vh;
  overflow-y: scroll;
}

.contents::-webkit-scrollbar {
  display: none;
}

.divider {
  border: 0;
  border-top: 1px solid rgba(255, 255, 255, 0.1);
  width: 100%;
}

@media screen and (max-width: 900px) {
  #app {
    flex-direction: column;
  }

  .contents {
    width: 100%;
    height: auto;
  }

  .divider {
    width: 100%;
  }
}
</style>
