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
                npm cache clean --force
                npm ci
                #npm run build
                pwd
                ls -la
                '''
            }
        }
    }
}