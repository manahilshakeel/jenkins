pipeline {
    agent any

    stages {
        stage('Install Maven') {
            steps {
                bat '''
                curl -L -o maven.zip https://downloads.apache.org/maven/maven-3/3.9.9/binaries/apache-maven-3.9.9-bin.zip
                tar -xf maven.zip
                set PATH=%CD%\\apache-maven-3.9.9\\bin;%PATH%
                mvn -v
                '''
            }
        }
    }
}
