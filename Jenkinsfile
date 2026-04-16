pipeline {
    agent any

    stages {
        stage('Checkout SCM') {
            steps {
                // Update to the correct branch name (main instead of master)
                git branch: 'main', url: 'https://github.com/Govardhankm12/MyMavenFirefox.git'
            }
        }

        stage('Build') {
            steps {
                script {
                    sh 'mvn clean package'
                }
            }
        }

        stage('Run Tests') {
            steps {
                script {
                    // Ensure FirefoxDriver works
                    'mvn exec:java'           
                }
            }
        }
    }
    
    post {
        always {
            cleanWs()
        }
    }
}
