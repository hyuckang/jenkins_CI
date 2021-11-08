node {
     stage('Clone') {
         checkout scm
     }
     stage('Build') {
	# 빌드할 이미지명은 자신의 Docker Hub 계정을 넣어주어야 합니다.	
         app = docker.build("hyuckang/jenkins_ci")
     }
     stage('Push') {
         docker.withRegistry('<https://registry.hub.docker.com>', 'docker_hub') {
             app.push("${env.BUILD_NUMBER}")
             app.push("latest")
         }
     }
 }

