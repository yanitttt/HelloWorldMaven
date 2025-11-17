pipeline {
    agent any 
    stages {
        stage('Build') { 
            steps {
                // Utiliser Maven directement sans withMaven
                sh "mvn clean compile"
            }
        }
        stage('Test'){
            steps {
                // Utiliser Maven directement sans withMaven
                sh "mvn test"
            }
        }
        stage('build && SonarQube analysis') {
            steps {
                withSonarQubeEnv('sonar.tools.devops.****') {
                    sh 'sonar-scanner -Dsonar.projectKey=myProject -Dsonar.sources=./src'
                }
            }
        }
        stage("Quality Gate") {
            steps {
                timeout(time: 1, unit: 'HOURS') {
                    waitForQualityGate abortPipeline: true
                }
            }
        }
        stage('Deploy') {
            steps {
               // Utiliser Maven directement sans withMaven
               sh "mvn deploy"
            }
        }
    }
}
