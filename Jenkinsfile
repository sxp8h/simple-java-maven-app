pipeline {
    agent any
    stages {
        stage('Build o no') {
            steps {
                sh 'mvn -B -DskipTests clean package'
            }
        }
        stage('Test para pardillos') {
            steps {
                sh 'mvn test'
            }
            post {
                always {
                    junit 'target/surefire-reports/*.xml'
                }
            }
        }
        stage('Deliver lo top') {
            steps {
                sh './jenkins/scripts/deliver.sh'
            }
        }
    }
}
