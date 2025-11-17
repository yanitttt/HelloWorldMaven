pipeline {
    agent any 
    stages {
        stage('Checkout') {
            steps {
                // Récupère le code source depuis ton repository Git
                git url: 'https://github.com/yanitttt/HelloWorldMaven.git', branch: 'master'
            }
        }
        stage('Build') {
            steps {
                // Utiliser Maven directement sans withMaven
                sh "mvn clean compile"  // Exécute le build Maven
            }
        }
        stage('Test'){
            steps {
                // Utiliser Maven directement sans withMaven
                sh "mvn test"  // Exécute les tests avec Maven
            }
        }
        stage('Deploy') {
            steps {
                // Déploiement avec Maven
                sh "mvn deploy"  // Exécute le déploiement Maven
            }
        }
    }
}
