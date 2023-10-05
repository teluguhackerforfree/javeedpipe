pipeline {
    agent any

    stages {
        stage('code') {
            steps {
                git 'https://github.com/sunildevops77/maven.git'
            }
        }
		stage('compile') {
            steps {
                sh 'mvn compile'
            }
        }
		stage('package') {
            steps {
                sh 'mvn clean package'
            }
        }
		stage('deploy') {
            steps {
                deploy adapters: [tomcat9(credentialsId: 'pipelinetomcat', path: '', url: 'http://18.60.148.163:8081/')], contextPath: 'avanti', war: '**/*.war'
            }
        }
    }
}
