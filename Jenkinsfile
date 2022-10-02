pipeline{
           agent any
           environment {
                      DOCKERHUB_CREDENTIALS=credentials('dockerhub')
            }
           stages {
                stage('Build') {
                        steps {
                              sh 'docker build -t alolo1001/jenkins:latest .' 
                              }
                  }
                stage('Login') {
                        steps {
                                   sh 'echo 1alolo1## | docker login -u alolo1001 --password-stdin'
                              }
                 }
                stage('Push') {
                        steps {
                              sh 'docker push alolo1001/jenkins:latest'
                              }
                }
            }
          post {
              always {
                  sh 'docker logout'
                      }
            }
}
