node {
    stage('SCM checkout'){

    checkout scm
    }
    stage('Push to Docker Hub'){
    docker.withRegistry('https://registry.hub.docker.com', '13e71cec-8462-4498-ac65-9525d0f56ce1') {

        def customImage = docker.build("ananddwivedi2013/dockerwebapp1")

        /* Push the container to the custom Registry */
        customImage.push()
    }
    }
    stage('Stop container'){
    sh 'docker container stop webapp'
    sh 'docker container rm webapp'
    }
    stage('start container'){
    sh 'docker run -d --name webapp -p 5000:5000 ananddwivedi2013/dockerwebapp1'
    }
}
