node {
    stage 'checkout'
    git 'https://gitlab.com/RavisankarCts/hello-world.git' 
    
    stage 'build'
    sh 'mvn clean install'
    
    stage('Results - 1') {
         junit '**/target/surefire-reports/TEST-*.xml'
         archiveArtifacts 'target/*.jar'
    }
    
   
}
