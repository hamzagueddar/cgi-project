pipeline {
    agent any

    stages {
        stage('Clean') {
            steps {
                // Nettoie le projet
                withMaven(maven: 'maven') {
                    bat 'mvn clean'
                }
            }
        }

        stage('Compile') {
            steps {
                // Compile le projet
                withMaven(maven: 'maven') {
                    bat 'mvn compile'
                }
            }
        }

        stage('Test') {
            steps {
                // Exécute les tests
                withMaven(maven: 'maven') {
                    bat 'mvn test'
                }
            }
        }

        stage('Package') {
            steps {
                // Crée le package (par exemple, JAR ou WAR)
                withMaven(maven: 'maven') {
                    bat 'mvn package'
                }
            }
        }

        stage('Deploy') {
            steps {
                // Déploie le projet (cette étape dépend de votre configuration)
                withMaven(maven: 'maven') {
                    bat 'mvn deploy'
                }
            }
        }
    }

    post {
        success {
            echo 'Ceci sera exécuté uniquement si le pipeline réussit.'
        }
        failure {
            echo 'Ceci sera exécuté uniquement si le pipeline échoue.'
        }
        unstable {
            echo 'Ceci sera exécuté uniquement si le pipeline est instable.'
        }
    }
}
