//pipeline {
  //  agent any

    // environment {
    //     DOCKER_HUB_CREDENTIALS = credentials('ramyasritiru_jenkins')  // Update with your Docker Hub credentials ID
    //     IMAGE_NAME = 'my-node-app'
    //     DOCKERFILE_PATH = 'Dockerfile'  // Path to your Dockerfile relative to Jenkins workspace
    //     DOCKER_HUB_REPO = 'ramyasritiru/my-node-app'  // Update with your Docker Hub repository name
    // }

   // stages {
node {
        stage('Build and Push Image') {
            steps {
                script {
                    def dockerImage = docker.build("${env.DOCKER_HUB_REPO}:${env.BUILD_NUMBER}", "-f ${env.DOCKERFILE_PATH} .")

                    docker.withRegistry('https://registry.hub.docker.com', env.DOCKER_HUB_CREDENTIALS) {
                        dockerImage.push()
                    }
                }
            }
        }
    }
//}
