pipeline {
    agent any
    environment{
        imageName="foodapp"
    }
    stages {
        stage('Build') {
            steps {
                sh "docker build -t ${IMAGE_NAME}:${BUILD_NUMBER} ."
            }
        }
    }
}
