node {
    def dockerImage = 'node:16-buster-slim'

    stage('Build') {
        // Start Docker Container pada stage 'Build'
        withDockerContainer(image: dockerImage, args: '-p 3000:3000') {
            sh 'npm install'
        }
    }

    stage('Test') {
        // Start Docker Container pada stage 'Test'
        withDockerContainer(image: dockerImage, args: '-p 3000:3000') {
            sh './jenkins/scripts/test.sh'
        }
    }
    stage('Deliver') {
        // Start Docker Container pada stage 'Deliver'
        withDockerContainer(image: dockerImage, args: '-p 3000:3000') {
            sh './jenkins/scripts/deliver.sh'
        }
    }
}
