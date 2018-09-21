pipeline {
    agent any
    def username="wcq"
    stages {
        stage('Checkout') {
            steps {
                echo "${username}"
           }
        }        
        stage('Build') {
            steps {
                echo 'Building'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying'
            }
        }
    }
}
