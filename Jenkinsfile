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
                    npm ci
                    sudo chown -R 118:128 "/.npm"
                    npm run build
                    ls -la
                '''
            }
        }
    }
}
