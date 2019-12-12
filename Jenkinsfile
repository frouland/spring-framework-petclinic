pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Checkout...'
                git 'https://github.com/frouland/spring-framework-petclinic.git' 
                
            }
        }
        stage('Build') {
            steps {
                parallel(
                  build: {
                    echo 'Building...'
                    sh 'mvn clean install'
                    archiveArtifacts 'target/*.war'
                  },
                  sonar: {
                    echo "Analyse Sonar..."
                  }
                )                
            }
            
        }
        stage('Deploy') {
            steps {
                echo 'Deploying...'
                sh 'cp target/*.war /var/tmp'
            }
        }
    }
}
