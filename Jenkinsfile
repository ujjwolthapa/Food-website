pipeline {
    agent any
    environment{
        imageName="foodapp"
    }
    stages {
        stage('Build') {
            steps {
                sh "docker build -t ${imageName}:${BUILD_NUMBER} ."   
            }
    }
        stage('Clear old build'){
            steps {
                sh "docker rmi ${imageName}:(${BUILD_NUMBER}-1)"
            }
    }
}
