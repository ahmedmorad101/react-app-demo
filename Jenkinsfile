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
                #npm ci
                #npm run build
                ls -la /home/node
                '''
            }
        }
    }
}