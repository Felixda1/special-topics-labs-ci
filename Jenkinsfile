
node {
  stage('checkout sources') {
        // You should change this to be the appropriate thing
        git url: 'https://github.com/Felixda1/special-topics-labs-ci.git'
  }

  stage('Build') {
    withMaven (maven: 'maven3') {
              sh "mvn package"
            }
  }
      post {
          always {
              junit 'target/surefire-reports'
          }
      }
  }
