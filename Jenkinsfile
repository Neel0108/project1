pipeline {
    agent any

    stages {
        
        stage('Building') {
            steps {
                echo 'The Code will be now be built into an artifact'
            }
        }
        stage('Clone repository') {
          checkout scm
        }
      
        stage('Build Docker Image') {
            steps {
                script {
                  sh 'docker build -t neelkakadia/neelkakadia_my_app_1.0 .'
                }
            }
        }
      
        stage('Build image') {
          app = docker.build("Neel0108/project1")
        }
        
        stage('Test image') {
          app.inside {
            sh 'echo "Tests passed"'
          }
        }
    }   
}

//       stage('Push Docker Image') {
//            steps {
//                script {
//                    withCredentials([string(credentialsId: 'neelkakadia', variable: 'dockerhubpwd')]) {
    // some block   
//                    sh 'docker login -u neelkakadia -p $(dockerhubpwd)'

  //                  sh 'docker push neelkakadia/neelkakadia_my_app_1.0'
//                }
  //          }
     //   } 
    