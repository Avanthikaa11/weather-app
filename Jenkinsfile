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

   
    stage('Deploy') {
        steps {
            bat '''
                set "PATH=%JAVA_HOME%\\bin;%PATH%"

                mvn deploy -DskipTests -s "C:\\Program Files\\Jenkins\\settings.xml"
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
