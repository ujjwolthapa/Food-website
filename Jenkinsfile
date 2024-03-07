pipeline {
    agent any
    environment {
        imageName = "registry.bromx.com:8050/gitops/foodapp"
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
                withCredentials([string(credentialsId: 'docker-registry', variable: 'USER'),string(credentialsId: 'credPassName', variable: 'PASS')]) 
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
