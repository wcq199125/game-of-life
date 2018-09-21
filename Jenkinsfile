pipeline {
    agent any
    properties([gitLabConnection('Gitlab'),
    parameters([choice(choices: "uat\nprod", description: 'deploy to environment', name: 'DEPLOY_ENV'),
        booleanParam(defaultValue: true, description: 'compile package and build docker image', name: 'BUILD_STEP')]),
    ])
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
