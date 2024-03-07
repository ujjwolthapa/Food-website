pipeline {
    agent any
    environment {
        imageName = "bromx.tail9b71d.ts.net/gitops/foodapp"
        oldTag = "${BUILD_NUMBER.toInteger() - 1}"
    }
    stages {
        stage('Build') {
            steps {
                sh "docker build -t ${imageName}:${BUILD_NUMBER} ."   
            }
        }
        stage('Login'){
            steps{
                withCredentials([string(credentialsId: 'registry-user', variable: 'USER'),string(credentialsId: 'registry-password', variable: 'PASS')]) 
                {
                    sh "docker login bromx.tail9b71d.ts.net -u $USER -p $PASS"
                }

            }
        }
         stage('Push'){
            steps{
               sh "docker push ${imageName}:${BUILD_NUMBER}"

            }
        }
    }
}
