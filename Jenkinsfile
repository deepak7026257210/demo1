pipeline {
    agent any {
     
    stages {
        stage('clone repo') {
            steps {
                echo 'Clone repo'
                sh " git clone https://github.com/jenkins-docs/simple-java-maven-app"
            }
        }
        stage('build') {
            steps {
                 dir('simple-java-maven-app'){
                    sh("mvn clean install")
                 }
            }
        }
        stage('test') {
            steps {
                 dir('simple-java-maven-app'){
                    sh("mvn test")
                 }
            }
        }
        stage('Deliver') {
            steps {
                dir('simple-java-maven-app'){
                sh './jenkins/scripts/deliver.sh'
                }
             }
          }
    }
  }
}


