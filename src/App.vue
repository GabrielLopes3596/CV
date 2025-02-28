<!-- App.vue -->
<template>
  <div id="app">
    <header>
      <h1>{{ personalInfo.name }}</h1>
      <h2>{{ personalInfo.title }}</h2>
      <div class="contact-info">
        <p>
          <span class="personalInfo mdi mdi-email-outline"></span>
          {{ personalInfo.email }} |
          <span class="personalInfo mdi mdi-cellphone"></span>
          {{ personalInfo.phone }} |
          <span class="personalInfo mdi mdi-cake-variant"></span>
          {{ personalInfo.birthday }}
        </p>
        <p>
          <span class="personalInfo mdi mdi-home"></span>
          {{ personalInfo.location }}
        </p>
        <p>
          <span class="personalInfo mdi mdi-linkedin"></span
          ><a :href="personalInfo.linkedIn">LinkedIn</a>
        </p>
      </div>
    </header>

    <section>
      <h2>About me <span class="mdi mdi-account-circle"></span></h2>
      <p v-for="detail in aboutMe.details" class="job">
        {{ detail }}
      </p>
      <p><strong>Hobbies:</strong> {{ aboutMe.hobbies.join(", ") }}</p>
    </section>

    <section>
      <h2>Core Technologies <span class="mdi mdi-chart-arc"></span></h2>
      <ul class="skills-list">
        <li v-for="(tech, index) in coreTechnologies" :key="index">
          {{ tech }}
        </li>
      </ul>
    </section>

    <section>
      <h2>
        Work Experience <span class="mdi mdi-account-supervisor-circle"></span>
      </h2>
      <div v-for="job in experience" :key="job.id" class="job">
        <h3>{{ job.title }} at {{ job.company }}</h3>
        <p class="job-date">{{ job.date }}</p>
        <ul>
          <li v-for="(achievement, index) in job.achievements" :key="index">
            {{ achievement }}
          </li>
        </ul>
        <br />
        <p>
          <strong>Technologies used:</strong> {{ job.technologies.join(", ") }}
        </p>
      </div>
    </section>

    <section>
      <h2>Academic Projects <span class="mdi mdi-hexagon-multiple"></span></h2>
      <div v-for="project in projects" :key="project.id" class="project">
        <h3>{{ project.name }}</h3>
        <p class="job-date">{{ project.date }}</p>
        <p>{{ project.description }}</p>
        <p>
          <strong>Technologies:</strong> {{ project.technologies.join(", ") }}
        </p>
        <p v-if="project.link"><a :href="project.link">View Project</a></p>
      </div>
    </section>

    <section>
      <h2>Education <span class="mdi mdi-account-school"></span></h2>
      <div v-for="edu in education" :key="edu.id" class="education">
        <h3>{{ edu.degree }}</h3>
        <p>{{ edu.institution }}, {{ edu.year }}</p>
      </div>
    </section>

    <section>
      <h2>Additional Skills <span class="mdi mdi-chart-donut"></span></h2>
      <ul class="skills-list">
        <li v-for="(skill, index) in additionalSkills" :key="index">
          {{ skill }}
        </li>
      </ul>
    </section>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      personalInfo: {
        name: "Gabriel Lopes",
        title: "Frontend Engineer",
        email: "gabrielsimoeslopes3596@gmail.com",
        phone: "(+351) 910780322",
        birthday: "23/04/1996",
        location: "Vila Nova de Gaia, Porto, Portugal",
        linkedIn: "https://www.linkedin.com/in/gabriel-lopes-877756148/",
      },
      aboutMe: {
        details: [
          "I am a person who finds great joy in forging new connections, meeting new people and embracing new opportunities for both personal and professional growth.",
          "Usually in my work I'm very focused on the quality of what is delivered and I have a keen eye to detail. I always look for a way to build and bring value with the work that I do, which is something that motivates me and gives me purpose. I am driven by a continuous pursuit of improvement, often engaging in self-reflection to refine my skills and enhance my contributions.",
          "Outside of the professional sphere, you'll often find me at the gym, where I channel my energy into staying physically healthy. Additionally, I am deeply committed to broadening my horizons, exploring diverse topics that catch my interest.",
        ],
        hobbies: [
          "Gaming",
          "Gym",
          "Technology",
          "Hangouts",
          "Cooking",
          "3D modeling",
        ],
      },
      summary:
        "Passionate Frontend Engineer with X years of experience in building responsive and user-friendly web applications. Skilled in modern JavaScript frameworks and committed to writing clean, efficient code.",
      coreTechnologies: [
        "JavaScript (ES6+)",
        "Vue.js",
        "AWS",
        "HTML5",
        "CSS/SCSS",
        "MongoDB",
        "Webpack",
        "Postman"
      ],
      experience: [
        {
          id: 1,
          title: "Engineering Manager",
          company: "Swogo, a 1WorldSync Company",
          date: "Aug 2024 - Current",
          achievements: [
            "Lead design approval for customer integration",
            "Communicate with the Product and Design teams to prepare Product Innovation plans and Roadmap",
            "Help internal teams with issues reported, creation of tasks and plan actionables",
            "Manage accounts and access control to our internal tools and code base",
            "Participate in calls to address potential customers and provide an overview on how the integration process works and the innerworks on the Engineering side",
            "Prepare and conduct interviews with potential candidates to hire to the team",
            "Communicate with the HR and Recruitment teams to assess potential candidates to hire",
            "Manage the team daily needs and plan the work to be done on each sprint/week",
            "Create and keep track of team KPIs and provide performance review to each team member",
            "Provide performance reviews, plan career paths and learning activities for the team",
            "Organize and prepare team events and team building activities",
          ],
          technologies: [
            "AWS",
            "Terraform",
            "JavaScript",
            "CSS/SCSS",
            "HTML5",
            "MongoDB",
          ],
        },
        {
          id: 2,
          title: "Frontend Engineer",
          company: "Swogo, a 1WorldSync Company",
          date: "Apr 2020 - Aug 2024",
          achievements: [
            "Led design approval, implementation and configuration tasks for customer integration",
            "Development of a Customer Portal, to allow customers to consult their performance",
            "Development of internal tools to improve our internal teams work and help optimize their tasks",
            "Part of the decision-making and implementation of tools rebranding",
            "Part of the development of a system for scraping complementary information from the customers' websites",
            "Participated in the implementation of a templating system to streamline UI integrations",
            "Responsible to maintain direct communication with customers to provide a smoother integration process",
            "Communicate with internal teams to document, define and refine integration processes",
            "Document internal processes, tools and projects' specifications",
          ],
          technologies: [
            "Vue.js",
            "Vuex",
            "JavaScript",
            "SCSS",
            "Jest",
            "HTML5",
            "MongoDB",
            "AWS",
          ],
        },
        // Add more job experiences
      ],
      projects: [
        {
          id: 1,
          date: "Oct 2018 - Jan 2019",
          name: "Medicine and Medical Prescription Management Application",
          description:
            "Development of the first version of a project, which contains ability, mission and inventory systems, navigation through map and minimap display, shop system through a NPC and enemies that might drop items when defeated.",
          technologies: [
            "Unreal Engine 4",
            "C++",
          ],
        },
        {
          id: 2,
          date: "Dec 2017 - Jan 2018",
          name: "Medicine and Medical Prescription Management Application",
          description:
            "Development of a web application that allows its users to access medicine information and manage medical prescriptions. Each user role had its own dashboard displaying relevant information and the system also includes the GDPR legal conditions.",
          technologies: [
            "Javascript",
            "HTML5",
            "CSS",
            "Angular5",
            "Node.js",
            "Bootstrap",
            "MongoDB",
            "Postman",
          ],
        },
        // Add more projects
      ],
      education: [
        {
          id: 1,
          degree: "Bachelor Degree in Informatics Engineering",
          institution: "Instituto Superior de Engenharia do Porto",
          year: "2014 - 2019",
        },
        // Add more education entries
      ],
      additionalSkills: [
        "RESTful APIs",
        "Agile/Scrum",
        "Git",
        "UI/UX Design Principles",
        "Performance Optimization",
        "JIRA"
      ],
    };
  },
};
</script>

<style scoped>
#app {
  font-family: Arial, sans-serif;
  line-height: 1.6;
  color: #333;
  max-width: 800px;
  margin: 0 auto;
  padding: 20px;
}

header {
  text-align: center;
  margin-bottom: 15px;
}

h1 {
  color: #2c3e50;
  margin-bottom: 5px;
}

h2 {
  color: #3498db;
  border-bottom: 2px solid #3498db;
  padding-bottom: 4px;
  margin-top: 15px;
  margin-bottom: 5px;
}

.contact-info {
  display: flex;
  flex-direction: column;
  align-items: center;
  font-size: 0.9em;

  p {
    display: flex;
    flex-direction: row;
    align-items: center;

    .personalInfo {
      padding: 0 4px;
      font-size: 1.2em;
    }
  }
}

section {
  margin-bottom: 20px;
}

.skills-list {
  display: flex;
  flex-wrap: wrap;
  list-style-type: none;
  padding: 0;
}

.skills-list li {
  background-color: #ecf0f1;
  border-radius: 3px;
  padding: 5px 10px;
  margin: 5px;
}

.job,
.project,
.education {
  margin-bottom: 20px;
}

.job-date {
  font-style: italic;
  color: #7f8c8d;
}

a {
  color: #3498db;
  text-decoration: none;
}

a:hover {
  text-decoration: underline;
}

ul {
  padding-left: 20px;
}

@media (max-width: 600px) {
  #app {
    padding: 10px;
  }

  h1 {
    font-size: 1.8em;
  }

  h2 {
    font-size: 1.4em;
  }
}
</style>
