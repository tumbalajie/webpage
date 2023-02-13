node {
    stage('Clone repository') {
        /* Let's make sure we have the repository cloned to our workspace */

        checkout scm
    }

    stage('Build image') {
       dockerImage = docker.build("airist/webpage:latest")
    }
    
    stage('Push image') {
        withDockerRegistry([ credentialsId: "dockerhub", url: "" ]) {
        dockerImage.push()
        }
    }    
}
