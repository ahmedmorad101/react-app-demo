pipeline { 
    agent any

    stages {
        stage('Build'){
            agent {
                docker{
                    image 'node:22-alpine'
                    reuseNode true
                }
            }
            steps{
                sh '''
                ls -la
                node --version
                npm --version
                chown -R 122:125 "/.npm"
                npm ci
                npm run build
                ls -la
                '''
            }
        }
    }
}