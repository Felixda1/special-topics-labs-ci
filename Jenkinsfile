
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
  stage('Test') {
              steps {
                  sh './src/test/java/edu/cscc/topics/quality/unit check'
              }
          }
      }
      post {
          always {
              junit 'src/test/results.xml'
          }
      }
  }
}
