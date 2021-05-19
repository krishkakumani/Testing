node {
   def mavenHome = tool name: "maven3.6.2"
   stage('Checkoutcode'){
     git url: 'https://github.com/MithunTechnologiesDevOps/maven-web-application.git',branch: 'master'
   }
   
   stage('Build'){
      sh "${mavenHome}/bin/mvn clean package"
   }

   stage('SonarQubeserverReport'){
     withSonarQubeEnv('sonarqubeserver'){      
            sh "${mavenHome}/bin/mvn sonar:sonar"
     }
   }
}
