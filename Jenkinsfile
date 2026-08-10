pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                echo 'Checking out source code...'

                git branch: 'main',
                    url: 'https://github.com/SurajChaudhari-67/jenkins-cicd-demo.git'
            }
        }

        stage('Build') {
            steps {
                echo 'Starting build...'

                sh '''
                    echo "Build started"
                    echo "Repository contents:"
                    ls -la
                    echo "Build completed successfully"
                '''
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'

                sh '''
                    test -f README.md
                    echo "README.md found"
                    echo "Tests completed successfully"
                '''
            }
        }
    }

    post {
        success {
            echo 'CI/CD Pipeline completed successfully!'
        }

        failure {
            echo 'CI/CD Pipeline failed!'
        }
    }
}
