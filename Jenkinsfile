node {
  stage ('Clone Repository') {
  checkout scm
      }
  stage ('Build a Docker Image'){
    sh "sudo docker build -t kago_exam:2.0 ."
  }
  stage ('Push Image to Docker Hub'){
  sh "sudo docker login -u 'gideonkago' -p 'Kitale12345' "
  sh "sudo docker tag kago_exam:2.0 gideonkago/kago_exam:2.0"
  sh "sudo docker push gideonkago/kago_exam:2.0"
  }
  stage ('Deploy Docker Image'){
  sh "sudo docker container run --detach --publish 8002:80 --name web6 gideonkago/kago_exam:2.0"
  }
}
