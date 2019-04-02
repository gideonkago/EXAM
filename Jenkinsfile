node {
  stage ('Clone Repository') {
  checkout scm
      }
  stage ('Build a Docker Image'){
  sh "sudo docker build -t kago_exam:1.0 ."
  }
  stage ('Push Image to Docker Hub'){
  sh "sudo docker login -u 'gideonkago' -p 'Nakuru12345' "
  sh "sudo docker tag kago_exam:1.0 gideonkago/kago_exam:1.0"
  sh "sudo docker push gideonkago/kago_exam:1.0"
  }
  stage ('Deploy Docker Image'){
  sh "sudo docker container run --detach --publish 2280:80 --name kago_exam_3 gideonkago/kago_exam:1.0"
  }
}
