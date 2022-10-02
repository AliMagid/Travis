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
                              sh 'echo $DOCKERHUB_CREDENTIALS_PSW | sudo docker login -u $DOCKERHUB_CREDENTIALS --password-stdin'
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
