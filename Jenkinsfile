node{
    def buildNumber = BUILD_NUMBER
    stage("Git CheckOut"){
        git url: 'https://github.com/krishkakumani/Testing.git',branch: 'master'
    }
    
    stage(" Maven Clean Package"){
      def mavenHome =  tool name: "Maven-3.6.2", type: "maven"
      def mavenCMD = "${mavenHome}/bin/mvn"
      sh "${mavenCMD} clean package"
    } 

   stage('SonarQubeserverReport'){
     withSonarQubeEnv('sonarqubeserver'){      
            sh "${mavenHome}/bin/mvn sonar:sonar"
     }
   }
}
