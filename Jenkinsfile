node {
    
  environment {
    registry = "prathmeshrajmane/dockerwebappt"
    registryCredential = 'dockerhub'
    dockerImage = ''

  }
    checkout scm

    docker.withRegistry('https://registry.hub.docker.com', 'dockerHub') {

        def customImage = docker.build("prathmeshrajmane/dockerwebapp")

        /* Push the container to the custom Registry */
        customImage.push()
    }
}
