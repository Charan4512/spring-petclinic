pipeline{
    agent {
        label 'mac'
        //docker 'maven:3.5-alpine' --> Can be used when we install docker in the agent
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
                archiveArtifacts artifacts:'target/*.jar', fingerprint: true
             }
         }
    }
}
