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
                echo 'Building...'
                sh 'mvn clean install'
                archiveArtifacts 'target/*.war'
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
