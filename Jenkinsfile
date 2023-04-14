pipeline {
    // agent{label "linux"}
    agent any
    stages{
        stage("build"){
            steps{
                sh """docker build -t hello_there . """
            }
        }
        stage("run"){
            steps{
                sh """docker run --name JenkinsPipeline hello_there"""
            }
        }
        //  stage('docker login') {
        //     steps {
        //         sh 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'
        //     }
        // }
        // stage('docker push') {
        //     steps {
        //         sh 'docker push lloydmatereke/jenkins-docker-hub'
        //     }
        // }
        // https://sweetcode.io/how-to-build-and-push-docker-images-to-docker-hub-using-jenkins-pipeline/
    }
}