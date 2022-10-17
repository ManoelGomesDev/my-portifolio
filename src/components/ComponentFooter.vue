<template>
    
        <v-row class="align-center  footer" justify="center">
            <v-col cols="12" md="4" align-self="center" >
                <p>My social media links:</p>
                <v-icon color="white ">mdi-linkedin</v-icon>
                <v-icon color="white" class="ml-3">mdi-whatsapp</v-icon>
                <v-icon color="white" class="ml-3">mdi-instagram</v-icon>
                <v-icon color="white" class="ml-3">mdi-email</v-icon>
            </v-col>
           
            <v-col cols="12" md="4" align-self="center">
                <p>More projects I've worked on</p>
                <v-row align="center">
                    <v-icon color="white">mdi-github</v-icon>
                    <p>@ManoelLucioDev on GitHub.com</p>
                </v-row>
            </v-col>
        </v-row>
    
</template>

<style scoped>
.footer {
    padding: 20px 0;
    background-color: #4F47C8;
}

p{
    font-size: 12px;
    color: white;
}

</style>