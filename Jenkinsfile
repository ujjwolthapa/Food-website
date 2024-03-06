pipeline {
    agent any
    environment{
        imageName="foodapp"
    }
    stages {
        stage('Build') {
            steps {
                sh "docker build -t ${imageName}:${BUILD_NUMBER} ."
                echo "Build complete"
            }
        }
    }
}
