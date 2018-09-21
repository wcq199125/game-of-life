pipeline {
    agent any
    environment{
       CC="ewe" 
    }
    stages {
        stage('Checkout') {
            steps {
                echo "${CC}"
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
