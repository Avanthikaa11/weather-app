pipeline {
agent any

environment {
    JAVA_HOME = 'C:\\Program Files\\Zulu\\zulu-17'
}

stages {

    stage('Build') {
        steps {
            bat '''
                set "PATH=%JAVA_HOME%\\bin;%PATH%"

                echo JAVA_HOME=%JAVA_HOME%
                where java
                java -version
                mvn -version

                mvn clean package -DskipTests
            '''
        }
    }

    stage('Test') {
        steps {
            bat '''
                set "PATH=%JAVA_HOME%\\bin;%PATH%"

                java -version
                mvn test
            '''
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
        echo 'Weather application pipeline completed successfully in Jenkins'
    }

    failure {
        echo 'Weather application pipeline failed in Jenkins'
    }
}

}
