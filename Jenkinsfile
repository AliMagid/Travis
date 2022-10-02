pipeline{
           agent any
           environment {
                      DOCKERHUB_CREDENTIALS=credentials('dockerhub')
            }
           stages {
                stage('Build') {
                        steps {
                              sh 'sudo docker build -t alolo1001/jenkins:latest .' 
                              }
                  }
                stage('Login') {
                        steps {
                              sh 'echo $DOCKER_PASSWORD | sudo docker login -u $DOCKER_USERNAME --password-stdin'
                              }
                 }
                stage('Push') {
                        steps {
                              sh 'sudo docker push alolo1001/jenkins:latest'
                              }
                }
            }
          post {
              always {
                  sh 'docker logout'
                      }
            }
}
