pipeline {
    agent any

    stages {
        stage('Build') {
            agent {
                docker {
                    image 'node:18-alpine'
                    reuseNode true
                }
            }
            steps {
                sh '''
                    ls -la
                    node --version
                    npm --version
                    set -ex
                    export NPM_CONFIG_CACHE=$(pwd)/.npm-cache
                    npm ci
                    npm run build
                    ls -la
                '''
            }
        }
    }
}

