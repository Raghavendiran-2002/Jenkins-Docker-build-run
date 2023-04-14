pipeline {
    // agent{label "linux"}
    agent any
    environment {
        DOCKERHUB_CREDENTIALS = credentials('dockerhub')
    }
    stages{
        stage("build"){
            steps{
                sh """docker build -t raghavendiran2002/hello_there . """
            }
        }
        stage("run"){
            steps{
                sh """docker run --name JenkinsPipeline jenkins-docker-hub"""
            }
        }
         stage('docker login') {
            steps {
                sh 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'
            }
        }
        stage('docker push') {
            steps {
                sh 'docker push raghavendiran2002/jenkins-docker-hub'
            }
        }
        // https://sweetcode.io/how-to-build-and-push-docker-images-to-docker-hub-using-jenkins-pipeline/
    }
}