node {
    stage 'checkout'
    git 'https://github.com/frouland/spring-framework-petclinic.git' 
    
    stage ('build') {
        sh 'mvn clean install'
        archiveArtifacts 'target/*.war'
    }
    
    stage('deploy') {
         sh 'cp target/*.war /var/tmp'
    }
   
}
