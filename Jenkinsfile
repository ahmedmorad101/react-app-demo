pipeline { 
    agent any

    stages {
        stage('Build'){
            agent {
                docker{
                    image 'node:22'
                    reuseNode true
                }
            }
            steps{
                sh '''
                npm ci
                #npm run build
                pwd
                ls -la
                '''
            }
        }
    }
}