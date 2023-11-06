pipeline{
    agent any;
    stages{
        stage('build'){
	environment {
        DOCKER_IMAGE = "prathmeshrajmane/docker-test:${BUILD_NUMBER}"
        REGISTRY_CREDENTIALS = credentials('docker-cred')
             }
            steps{
                sh 'pwd'
                sh 'cd /c/Users/prajmane/k8s/dockerwebapp'
                sh 'ls'
                sh 'docker build -t ${DOCKER_IMAGE} .'
                def dockerImage = docker.image("${DOCKER_IMAGE}")
                docker.withRegistry('https://index.docker.io/v1/', "docker-cred") {
                dockerImage.push()
            }
        }
    }
}
