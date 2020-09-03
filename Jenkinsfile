pipeline {
  agent any
  stages {
    stage('Git') {
      steps {
        build '1 RunDevelopmentProjectBuild'
      }
    }

    stage('Tx_Automation') {
      parallel {
        stage('Tx_Api') {
          steps {
            build '2 RunAutomationTests_API'
          }
        }

        stage('Tx_Web') {
          steps {
            build '3 RunAutomationTests_Web'
          }
        }

        stage('Tx_Mobile') {
          steps {
            build '4 RunAutomationTests_Mobile'
          }
        }

        stage('Performance ') {
          steps {
            build '5 Performance_Tests'
          }
        }

      }
    }

    stage('SonarQube') {
      steps {
        build '6 RunAutomationTests_SonarQube'
      }
    }

  }
}