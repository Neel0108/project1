pipeline {
    agent any
    
    environment {
		DOCKERHUB_CREDENTIALS=credentials('dockerhub')
	}

    stages {
        
        stage('Building') {     
            steps {
                echo 'The Code will be now be built into an artifact'
            }
        }
       /* stage('Clone repository') {
            steps {
                script {
                    sh 'git clone https://github.com/Neel0108/project1.git'
                }
            }
        } */
        stage('Build Image') {
            steps {
                script {
                    sh 'docker build -t neelkakadia_image .'
                }
            }
        }
        stage('Docker Login') {
            steps {
                script {
                    sh 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'
                }
            }
        }
        stage('Push Image'){
            steps {
                script {
                    sh 'docker push neelkakadia_image'
                }
            }
        }
    }
}      
   /*     stage('Build Docker Image') {
            steps {
                script {
                  sh 'docker build -t neelkakadia/neelkakadia_my_app_1.0 .'
                }
            }
        }       
      
        stage('Build image') {
            steps {
                    app = docker.build("Neel0108/project1/test")
            }
        }
        
        stage('Test image') {
            steps {
              app.inside {
                  script {
                    sh 'echo "Tests passed" '
                  }
              }
            }
        } */

//       stage('Push Docker Image') {
//            steps {
//                script {
//                    withCredentials([string(credentialsId: 'neelkakadia', variable: 'dockerhubpwd')]) {
    // some block   
//                    sh 'docker login -u neelkakadia -p "$(dockerhubpwd)" '

  //                  sh 'docker push neelkakadia/neelkakadia_my_app_1.0'
//                }
  //          }
     //   } 
    
