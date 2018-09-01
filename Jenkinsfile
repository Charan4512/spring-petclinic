pipeline{
    agent {
        label 'mac'
        docker 'maven:3.5-alpine'
    }
    stages{
        stage('Checkout') {
            steps {
                git 'https://github.com/Charan4512/spring-petclinic.git'
            }
        }

        stage('Build') {
             steps {
                sh 'mvn clean package'
                junit '**/target/surefire-reports/TEST-*.xml'
             }
         }
    }
}
