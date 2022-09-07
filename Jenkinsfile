pipeline{
  agent any
  stages{
  	stage('version-control'){
  		steps{
  			checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'gitub-id', url: 'https://github.com/Bonji-Tech/ba-team3-multbranchApp.git']]])
  		}
  	}
    stage('parallel-job'){
      parallel{
        stage('sub-job1'){
          steps{
            echo 'action1'
          }
        }
        stage('sub-job2'){
          steps{
            echo 'action2'
          }
        }
        stage('sub-job3'){
            steps{
                echo 'action3'
            }
        }
        stage('user-check'){
          steps{
            sh 'cat /etc/passwd | grep jenkins'
          }
        }
      }
    }
    stage('2-parallel'){
        parallel {
          stage('to-test-multi-build'){
            steps{
              sh 'lscpu'
          }
        }
      }
    }
    stage('codebuild'){
    	steps{
    		sh 'cat /etc/passwd'
    	}
    }
  }
}
