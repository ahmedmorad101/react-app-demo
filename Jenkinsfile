pipeline { 
    agent any

    stages {
        stage('Build'){
            agent {
                docker{
                    image 'node:22'
                    args '-u root:root'
                    reuseNode true
                }
            }
            steps{
                sh '''
                npm ci
                npm run build
                ls -la
                '''
            }
        }

        stage('Test'){
            agent {
                docker{
                    image 'node:22'
                    args '-u root:root'
                    reuseNode true
                }
            }
            steps{
                sh '''
                test -f dist/index.html
                npm test
                '''
            }
        }
    }
}