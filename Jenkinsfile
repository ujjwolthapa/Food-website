pipeline {
    agent any
    environment {
        imageName = "foodapp"
        oldTag = "${BUILD_NUMBER.toInteger() - 1}"
    }
    stages {
        stage('Build') {
            steps {
                sh "docker build -t ${imageName}:${BUILD_NUMBER} ."   
            }
        }
        stage('Clear old build') {
            steps {
                sh "docker rmi ${imageName}:${oldTag}"
            }
        }
    }
}
