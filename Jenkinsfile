pipeline {
    agent any
    
    set JAVA_HOME=C:\Program Files\Zulu\zulu-17
set PATH=%JAVA_HOME%\bin;%PATH%

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