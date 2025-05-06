pipeline {
  agent any  //{label 'linux'}
  options {
    buildDiscarder(logRotator(numToKeepStr: '5'))
  }
  stages {
    stage('Hello') {
      steps {
        echo "hello"
      }
    }
    stage('Cat readme'){
      when {
        branch "fix-*"
      }
      steps{
        sh '''
          cat README.md
        '''
      }
    }
  }
}
//    stage('Build') {
//      steps {
//        sh './gradlew clean check --no-daemon'
//      }
//    }
//  }

//  post {
//    always {
//        junit(
//          allowEmptyResults: true, 
//          testResults: '**/build/test-results/test/*.xml'
//        )
//    }
//  }
//}
