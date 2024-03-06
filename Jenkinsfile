pipeline {
    agent any
    environment{
        imageName="foodapp"
    }
    stages {
        stage('Build') {
            steps {
                sh "docker build -t ${imageName}:${BUILD_NUMBER} ."
                echo "go please"
                echo "now go please"
                echo "aaba ja la ki"
                echo " gaideu ekchoti matra"
                
            }
        }
    }
}
