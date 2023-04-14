pipeline {
    // agent{label "linux"}
    agent any
    environment {
        DOCKERHUB_CREDENTIALS = credentials('dockerhub')
    }
    stages{
        stage('login docker') {
            steps {
                sh 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'
            }
        }
        stage("build"){
            steps{
                sh """docker build -t raghavendiran2002/jenkins-docker-hub . """
            }
        }
        stage('docker push') {
            steps {
                sh 'docker push raghavendiran2002/jenkins-docker-hub'
            }
        }
        stage("run"){
            steps{
                sh """docker run --name jenkinsdocker raghavendiran2002/jenkins-docker-hub"""
            }
        }
        stage('logout logout') {
            steps {
                sh 'docker logout'
            }
        }
        // https://sweetcode.io/how-to-build-and-push-docker-images-to-docker-hub-using-jenkins-pipeline/
    }
}