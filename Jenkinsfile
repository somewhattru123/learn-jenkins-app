pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                sh '''
                    echo "Hello World"
                    ls -la
                    '''
            }
        }

        stage('Simple with Docker') {
            agent {
                docker {
                    image 'node:18-alpine'
                    reuseNode true
                }
            }
            steps {
                sh '''
                    echo "Running inside Docker container"
                    ls -la
                    node -v
                '''
            }
        }
    }
}

