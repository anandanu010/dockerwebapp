node {

    checkout scm

    docker.withRegistry('https://registry.hub.docker.com', '13e71cec-8462-4498-ac65-9525d0f56ce1') {

        def customImage = docker.build("ananddwivedi2013/dockerwebapp")

        /* Push the container to the custom Registry */
        customImage.push()
    }
    stage('start container'){
    sh 'docker run -d -p 8000:8000 ananddwivedi2013/dockerwebapp'
    }
}
