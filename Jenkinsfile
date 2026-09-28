pipeline {
    agent any
    
    tools { jdk 'Zulu-17' maven 'Maven-3.9.12' }

    stages {

        stage('Build') {
            steps {
                bat 'mvn clean package -DskipTests'
            }
        }

        stage('Test') {
            steps {
                bat 'mvn test'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Weather Mule application deployment stage'
            }
        }
    }

    post {
        success {
            echo 'Weather application pipeline completed successfully'
        }

        failure {
            echo 'Weather application pipeline failed in jenkins'
        }
    }
}
