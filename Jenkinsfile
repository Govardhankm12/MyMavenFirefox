pipeline {
    agent any

    stages {
        stage('Checkout SCM') {
            steps {
                git branch: 'main', url: 'https://github.com/Govardhankm12/MyMavenFirefox.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Run Tests') {
            steps {
                sh 'mvn exec:java'
            }
        }
    }
    
    post {
        always {
            cleanWs()
        }
    }
}
