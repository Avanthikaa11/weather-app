pipeline {
agent any

environment {
    JAVA_HOME = 'C:\\Program Files\\Zulu\\zulu-17'
}

stages {

    stage('Clean') {
        steps {
            bat '''
                set "PATH=%JAVA_HOME%\\bin;%PATH%"

                mvn clean
            '''
        }
    }

    stage('Package') {
        steps {
            bat '''
                set "PATH=%JAVA_HOME%\\bin;%PATH%"

                mvn package -DskipTests
            '''
        }
    }

    stage('Test') {
        steps {
            bat '''
                set "PATH=%JAVA_HOME%\\bin;%PATH%"

                mvn test
            '''
        }
    }

    stage('Verify') {
        steps {
            bat '''
                set "PATH=%JAVA_HOME%\\bin;%PATH%"

                mvn verify -DskipTests
            '''
        }
    }

    stage('Deploy') {
        steps {
            bat '''
                set "PATH=%JAVA_HOME%\\bin;%PATH%"

                mvn deploy -DskipTests
            '''
        }
    }
}

post {
    success {
        echo 'Weather Mule application pipeline completed successfully'
    }

    failure {
        echo 'Weather Mule application pipeline failed'
    }
}
}
