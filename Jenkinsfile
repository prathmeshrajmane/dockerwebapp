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
            }
        }
	stage('Docker Push') {
    	agent any
      steps {
      	withCredentials([usernamePassword(credentialsId: 'docker-cred', passwordVariable: 'dockerHubPassword', usernameVariable: 'dockerHubUser')]) {
          sh "docker login -u ${env.dockerHubUser} -p ${env.dockerHubPassword}"
          sh 'docker push ${DOCKER_IMAGE}'
        }
      }
    }
}
}
