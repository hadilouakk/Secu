pipeline{  
  agent any
  stages {
    stage("Supprimer le workspace"){
      steps{
        deleteDir()
      }
    }    
    stage("checkout SCM"){
      steps{
        sh 'https://github.com/hadilouakk/Secu.git'
      }
    }
    stage ('build image docker'){
      steps{
        script{
sh 'docker build -t -myimage_ngnix'
sh 'docker tag myimage_ngnix'

}
      }

    }
    stage ('Deploiement conteneur'){
      steps {
        sh'docker stop monapp'
        sh'docker rm monapp'
        sh'docker run -d --name monapp --hostname monapp -p 8099:80 'myimage nginx


          }
        }

  }
}
