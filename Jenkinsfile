node {
    stage('Clone repository') {
        git  branch: 'main', credentialsId: 'github_access_token', url: 'https://github.com/alkaline2018/jenkins-django.git'
    }
    stage('Build image') {
        dockerImage = docker.build("alkaline2018/web_count:v1.0", "web-count/")
    }
    stage('Push image') {
        withDockerRegistry([ credentialsId: "docker-access", url: "" ]) {
            dockerImage.push()
        }
    }
}
