pipeline { 
    agent any

    environment{
        NETLIFY_SITE_ID = '22efd7a8-63fc-45d5-a561-c633de352045'
        NETLIFY_AUTH_TOKEN = credentials('netlify-token')
    }

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
                npm run test
                '''
            }
        }


        stage('Deploy'){
            agent {
                docker{
                    image 'node:22'
                    args '-u root:root'
                    reuseNode true
                }
            }
            steps{
                sh '''
                npm install netlify-cli -g
                netlify --version
                netlify status
                '''
            }
        }
    }
}