pipeline {
    agent any

    environment {
        JAVA_HOME = 'C:\\Program Files\\Zulu\\zulu-17'
        MAVEN_OPTS = '-Djavax.net.ssl.trustStore=C:\\Users\\10361687\\maven-certs\\cacerts -Djavax.net.ssl.trustStorePassword=changeit'
    }

    stages {

        stage('Clean') {
            steps {
                bat '''
                    set "PATH=%JAVA_HOME%\\bin;%PATH%"

                 
                    mvn clean package -U
                '''
            }
        }

        stage('Deploy') {
            steps {
                bat '''
                    set "PATH=%JAVA_HOME%\\bin;%PATH%"


                    mvn deploy -DskipTests -s "C:\\Program Files\\Jenkins\\settings.xml" -e -U
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
