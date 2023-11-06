pipeline{
    agent any;
    stages{
        stage('run'){
            steps{
                sh 'pwd'
                sh 'cd /c/Users/prajmane/k8s/dockerwebapp'
                sh 'ls'
 docker.withRegistry('https://registry.hub.docker.com', 'dockerHub') {

        def customImage = docker.build("prathmeshrajmane/docker-test")

        /* Push the container to the custom Registry */
        customImage.push()
    }
            }
        }
    }
}
