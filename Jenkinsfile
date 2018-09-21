pipeline {
    agent any
    parameters {
         string(name:'GREETING',defaultValue:'hello',description:'test 1')
    }
    stages {
        stage('Checkout') {
            steps {
                echo "${params.GREETING}"
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
