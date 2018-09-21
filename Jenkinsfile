pipeline {
    agent any
    def username="wcq"
    echo "${username}"
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
