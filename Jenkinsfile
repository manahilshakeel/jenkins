pipeline {
    agent any

    //  Environment Variable
    environment {
        VERSION = "1.0"
    }

    //  Tools (Make sure name matches Jenkins config)
    tools {
        maven 'Maven'
    }

    // 🎛 Parameters
    parameters {
        booleanParam(name: 'executeTests', defaultValue: true, description: 'Run test stage?')
    }

    stages {

        //  Build Stage
        stage('Build') {
            steps {
                echo "Building version ${VERSION}"
                
                // For Windows
                bat 'mvn -v'
            }
        }

        //  Test Stage (Conditional)
        stage('Test') {
            when {
                expression { params.executeTests == true }
            }
            steps {
                echo 'Running Tests...'
                
                // Example command
                bat 'echo Tests executed'
            }
        }

        //Deploy Stage
        stage('Deploy') {
            steps {
                echo 'Deploying application...'
                
                bat 'echo Deployment done'
            }
        }
    }

    post {
        always {
            echo 'Pipeline completed successfully!'
        }
        success {
            echo 'Build succeeded ✅'
        }
        failure {
            echo 'Build failed ❌'
        }
    }
}
