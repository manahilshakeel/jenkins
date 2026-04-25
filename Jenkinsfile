pipeline {
    agent any

    environment {
        VERSION = "1.0"
    }

    tools {
        maven 'Maven'
    }

    stages {
        stage('Build') {
            steps {
                echo "Version is ${VERSION}"
                bat 'mvn -v'
            }
        }
    }
}
