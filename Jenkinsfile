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
                
                npm i
                #npm run build
                pwd
                ls -la
                '''
            }
        }
    }
}