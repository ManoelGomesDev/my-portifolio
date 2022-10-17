<template>
  <main>
    <v-container>
      <article>
      <v-row>
        <v-col cols="12" md="4" align-self="center">
          <h1 class="animate__animated animate__bounce">Hi, Manoel Lúcio</h1>
          <p>
            I am a software developer and here is my portfolio website. Here you
            will learn about my journey as a software developer.
          </p>
          <v-btn elevation="2" class="primary">Hire me</v-btn>
        </v-col>
        <v-spacer></v-spacer>
        <v-col cols="12" md="4">
          <v-img class="animate__animated animate__pulse animate__repeat-3 " src="../assets/photo.png" max-height="30rem" contain />
        </v-col>
      </v-row>
      <h1 class="container text-center mb-3" id="skill">Skills</h1>
      <v-row align-content="center" class="mb-5">
        <v-col cols="12" md="6">
          <p class="container text-center">
            I have a vast experience in the following web technologies
          </p>
          <v-row align-content="center">
            <ComponentTech
              v-for="tech in technologies"
              :key="tech.name"
              :tech="tech"
            />
          </v-row>
        </v-col>
        <v-spacer></v-spacer>
        <v-col cols="12" md="4" align-self="center">
          <v-img src="./../assets/skillsimage.png" max-width="20rem" contain />
        </v-col>
      </v-row>
      </article>
    </v-container>
    <article>
    <v-row class="projects py-7 px-10">
      <v-col cols="12" md="12" align-self="center">
        <v-row justify="center" class="mb-4">
          <v-icon color="#E84949">mdi-laptop</v-icon>
          <h4 class="section-title ml-2" id="project">Projects</h4>
        </v-row>
        <v-row justify="center" class="mb-4">
          <p>Some of my projects include:</p>
        </v-row>
      </v-col>
      <v-row>
        <v-col cols="12" md="4">
          <v-card flat outlined class="card" max-height="30rem">
            <v-img
              src="./../assets/project1.png"
              contain
              height="15rem"
              width="20rem"
              class="mx-auto"
            ></v-img>
            <v-card-text class="text-card"
              >Made a SPA to legal consultant using ReactJS</v-card-text
            >
            <v-card-text class="text-card">
              <v-icon class="mr-2" color="#0d54be">mdi-web</v-icon>
              <a href="https://duxlegalsolutions.netlify.app/" target="_blank"
                >Visit site</a
              >
            </v-card-text>
          </v-card>
        </v-col>
        <v-col cols="12" md="4">
          <v-card flat outlined class="card">
            <v-img
              src="./../assets/project1.png"
              contain
              height="15rem"
              width="20rem"
              class="mx-auto"
            ></v-img>
            <v-card-text class="text-card"
              >Made a SPA to legal consultant using ReactJS</v-card-text
            >
            <v-card-text class="text-card">
              <v-icon class="mr-2" color="#0d54be">mdi-web</v-icon>
              <a href="https://duxlegalsolutions.netlify.app/" target="_blank"
                >Visit site</a
              >
            </v-card-text>
          </v-card>
        </v-col>
        <v-col cols="12" md="4">
          <v-card flat outlined class="card">
            <v-img
              src="./../assets/project1.png"
              contain
              height="15rem"
              width="20rem"
              class="mx-auto"
            ></v-img>

            <v-card-text class="text-card"
              >Made a SPA to legal consultant using ReactJS</v-card-text
            >
            <v-card-text class="text-card">
              <v-icon class="mr-2" color="#0d54be">mdi-web</v-icon>
              <a href="https://duxlegalsolutions.netlify.app/" target="_blank"
                >Visit site</a
              >
            </v-card-text>
          </v-card>
        </v-col>
      </v-row>
    </v-row>
    </article>
   <article>
<h4 class="section-title my-6" id="contact">Contact me</h4>
     
      <v-row justify="center" class="container mb-5">
        <v-col cols="12" md="6" align-self="center">
        <v-img
          src="./../assets/contactme.png"
          contain
          height="15rem"
         
          class="mx-auto my-auto"
        ></v-img>
        </v-col>
        <v-spacer></v-spacer>
        <v-col cols="12" md="5" >
        <v-form ref="form" v-model="valid" @submit.prevent="sendEmail" lazy-validation>
          <v-text-field
            v-model="name"
            :counter="10"
            :rules="nameRules"
            label="Name"
            name="user_name"
            
            required
          ></v-text-field>

          <v-text-field
            v-model="email"
            :rules="emailRules"
            label="E-mail"
            name="user_email"
            
            required
          ></v-text-field>

          <v-textarea
            label="Your message"
            name="user_message"
            flat> </v-textarea>

          <v-btn
            :disabled="!valid"
            color="success"
            class="mr-4"
            @click="validate"
          >
            Send
          </v-btn>
        </v-form>
        </v-col>
     </v-row>
     </article>
    
    
  </main>
</template>
<script>
import ComponentTech from "@/components/ComponentTech.vue";
import emailjs from '@emailjs/browser';


export default {
  components: {
    ComponentTech,
  },
  data() {
    return {
      technologies: [
        { image: "html5.png", name: "HTML5" },
        { image: "css3.png", name: "CSS3" },
        { image: "javascript.png", name: "JavaScript" },
        { image: "bootstrap.png", name: "Bootstrap" },
      ],
      valid: true,
      name: '',
      nameRules: [
        v => !!v || 'Name is required',
        v => (v && v.length <= 10) || 'Name must be less than 10 characters',
      ],
      email: '',
      emailRules: [
        v => !!v || 'E-mail is required',
        v => /.+@.+\..+/.test(v) || 'E-mail must be valid',
      ],
    };
  },
  methods: {
      validate () {
        this.$refs.form.validate()
       
       
      },
      sendEmail(){
         emailjs.sendForm('gmailMessage', 'template_z6r9d6s', this.$refs.form, 'user_dtkC4ch8LJM5Hn531jJQb')
        .then((result) => {
            console.log('SUCCESS!', result.text);
        }, (error) => {
            console.log('FAILED...', error.text);
        });
      }
  }
};
</script>

<style scoped>
a {
  text-decoration: none;
}


.projects {
  background-color: #dcf6f8ac;
}

.card {
  background: rgb(233, 233, 233);
  border: 2px solid #0d54be;
}

.section-title {
  color: #e84949;
  font-size: 1.2rem;
  text-align: center;
}

.text-card {
  background: white;
  text-align: center;
}

</style>
