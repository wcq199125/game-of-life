pipeline {
    agent any
    parameters {
         string(name:'GREETING',defaultValue:'hello',description:'test 1');
         booleanParam(name: 'DEBUG_BUILD', defaultValue: true, description: '') 
    }
    stages {
        stage('Checkout') {
            steps {
                checkout scm
                echo "${params.DEBUG_BUILD}"
                echo "${params.GREETING}"
           }
        }        
        stage('Build') {
            steps {
            podTemplate(name: 'jenkins-slave-maven', label：'maven' , namespace: 'kube-system', idleMinutes: 30, containers: [
            containerTemplate(name: 'maven', image: 'maven:3.5-alpine', command: 'cat', ttyEnabled: true),
            containerTemplate(name: 'docker', image: 'docker:17.03-dind', 
                args: '--registry-mirror=https://registry.docker-cn.com -s=overlay2 --bip=172.30.1.1/24', privileged: true, ttyEnabled: true),
            containerTemplate(name: 'k8s', image: 'hub.simpletour.com/infra/jenkins-k8s', command: 'cat', ttyEnabled: true), 
        ],
        volumes:[
            secretVolume(secretName: 'docker-config', mountPath: '/home/jenkins/.docker'),
            secretVolume(secretName: 'jenkins-maven-settings', mountPath: '/root/.m2'),
            secretVolume(secretName: 'k8s-context', mountPath: '/home/jenkins/.kube'),
            hostPathVolume(mountPath: '/maven/repository', hostPath: '/data/nfs/maven-repo'),
            // persistentVolumeClaim(claimName: 'maven-repo', mountPath: '/maven/repository'),
        ]){
            node(label) {
                body()
            }
        }
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
