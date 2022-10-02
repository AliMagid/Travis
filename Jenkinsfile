pipeline{
           agent any
           environment {
                      DOCKERHUB_CREDENTIALS=credentials('dockerhub') # the ID of the docker credentials that you created in step 5
            }
           stages {
                stage('Build') {
                        steps {
                              sh 'docker build -t alolo1001/jenkins:latest .' # your docker hub name/repo
                              }
                  }
                stage('Login') {
                        steps {
                              sh 'echo $DOCKER_USERNAME | docker login -u $DOCKER_PASSWORD --password-stdin'
                              }
                 }
                stage('Push') {
                        steps {
                              sh 'docker push alolo1001/jenkins:latest' # your dockerhub name/repo
                              }
                }
            }
          post {
              always {
                  sh 'docker logout'
                      }
            }
}
