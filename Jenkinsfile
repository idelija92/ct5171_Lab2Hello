pipeline {
    agent any

    stages {
        stage('GetProject') {
            steps {
                git branch:'main', url: 'https://github.com/idelija92/ct5171_Lab2Hello.git'
            }
        }
        stage('Build') {
            steps {
                sh 'mvn clean:clean'
                sh 'mvn dependency:copy-dependencies'
                sh 'mvn compiler:compile'
            }
        }
        stage('Execute') {
            steps {
                sh 'mvn exec:java'
            }
        }
        stage('Package') {
            steps {
                sh 'mvn package'
            }
        }
    }
}