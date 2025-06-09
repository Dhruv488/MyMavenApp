pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // IMPORTANT: Replace with your actual GitHub repository URL for MyMavenApp
                // Make sure the branch name matches what you pushed (e.g., 'main')
                git branch: 'main', url: 'https://github.com/Dhruv488/MyMavenApp.git'
            }
        }
        stage('Build') {
            steps {
                sh 'mvn clean package' // Executes Maven build commands
            }
        }
        stage('Test') {
            steps {
                junit '**/target/surefire-reports/*.xml' // Publishes JUnit test results
            }
        }
        // You can add more stages here, e.g., for deployment if you expand the lab
    }
    post {
        always {
            echo 'Pipeline finished.'
        }
        success {
            echo 'Pipeline successful!'
        }
        failure {
            echo 'Pipeline failed! Check console output for details.'
        }
    }
}

