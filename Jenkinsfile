node {
    
    checkout scm

    docker.withRegistry('https://registry.hub.docker.com', 'dockerHub') {

        def customImage = docker.build("prathmeshrajmane/docker-test")

        /* Push the container to the custom Registry */
        customImage.push()
    }
}
